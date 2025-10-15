# Create Custom Alerts

Create custom alerts to get notified when your defined metrics reach a specific threshold. You can set the threshold, define how often alerts are checked and sent, and create rules that combine multiple conditions.

## Prerequisites

You’ve set up alerts and notifications in the Cloud Dashboard. For more information, refer to [Setting up alerts and notifications](https://example.com/guides/clouddashboard/alerts-and-notifications.html).

## Steps

1. Open the `Cloud Dashboard`.
2. Go to `Alerts` > `Custom Alerts`.
3. Click `Create Alert`.
4. Select the metric you want to track:  
   - `CPU Usage`  
   - `Memory`  
   - `Network`  
5. Set the threshold for the selected metric. For example:  
   - Memory > 85%  
   - CPU usage > 80%  
6. Set the check frequency to define how long the threshold must be exceeded before it triggers an alert. For example: 5 minutes.  
   **Note:** If you leave this field empty, the default value is 15 minutes.  
7. Under `Alert Frequency`, choose how often you want to receive notifications:  
   - `Immediately`  
   - `Daily`  
   - `Weekly`  
8. **Optional:** Create a rule to combine multiple conditions that must be met before an alert is triggered:  
   a) Open the `Advanced Options` tab.  
   b) Under `Custom Alert Rules`, define the rule using logical operators (`AND` or `OR`). Here’s an example custom alert rule:</br>
(CPU Usage > 80% for > 5 minutes) AND (Network thresholds > 66% for more than 15 minutes)</br>
   c) Select `OK`.
9. Save your changes.

## Result

Depending on the alert frequency you selected, you receive an alert in your inbox when a threshold is reached. The alert includes details about the metric that triggered it.