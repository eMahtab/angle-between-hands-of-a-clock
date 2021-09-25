# Angle Between Hands of a clock
## https://leetcode.com/problems/angle-between-hands-of-a-clock

Given two numbers, hour and minutes. Return the smaller angle (in degrees) formed between the hour and the minute hand.

```java
class Solution {
    public double angleClock(int hour, int minutes) {
        // In one minute, minute's hand makes 6 degree
        // In one minute, hour's hand makes 1/2 = 0.5 degree
        double hoursHand = ((hour % 12) * 60 + minutes) / 2.0;
        int minutesHand = minutes * 6;
        double angle = Math.abs(hoursHand-minutesHand);
        if(angle <= 180)
            return angle;
        double min = Math.min(hoursHand, minutesHand);
        double max = Math.max(hoursHand, minutesHand);
        angle = (360 - max) + min;
        return angle;
            
    }
}
```
