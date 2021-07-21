+++
title = "7.4 Observe the Impact"
chapter = true
weight = 30
+++

# Observe the Impact

While the attack is running, open the website in a browser and try using it like a regular user. Do you see anything unusual?

- How is the user experience? Is the website slow, unresponsive, or working fine?
- If there is a failure, does your UI handle the failure in a way that's acceptable for your customers?
- Was your hypothesis correct?
- Did you hit your abort conditions? Did you halt the experiment?

Chances are when you ran this experiment, you saw the following screen:

![Sock Shop Results](/images/blackhole_results1.png)
![Sock Shop Results](/images/blackhole_results2.png)

Customers would not be happy to see this. The page is clearly not working, but there aren't any notifications or error messages explaining why. Ideally we would have some form of redundancy to prevent this from happening in the first place.

If you haven't already, make sure to press the halt button in Gremlin to stop the experiment:

![Gremlin UI - Halt](/images/gremlin_ui_halt_explanation.png)

We expected something like this to happen in our hypothesis, and now we've verified it. We found and demonstrated the failure mode before it could become a real production outage. We can now work on adding fixes to prevent this problem from happening again, then repeat the experiment to make sure those fixes are effective.

One last action item to consider: did you see any indication of the outage in CloudWatch? If not, you might want to see which metrics could detect an issue like this and create an alert so that your team is notified if this happens again.