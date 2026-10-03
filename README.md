
<h1>Entra-ID monitoring with splunk</h1>


<h2>Description</h2>

This demonstrates the implementation and management of user-risk policies in Microsoft Entra-ID. I should state that I do not have the Microsoft Entra-ID premium P2 licence to operate, however, this walk through will have captions which should clearly explain what is happening.

-The user-risk policy analyses the probability that user's account has been compromised by detecting risk events that are atypical of a user's behaviour.

-The sign-in risk policy evaluates the probability that a specific authentication event is unauthorised.

-Multi-factor registration policy provides a second layer to user sign-ins. A means to verify who you are more than just the username and password. 
<br />


<h2>Walk-through:</h2>
<h3>Enable user-risk policy</h3>

<p align="center">
Sign-in to Microsoft Entra adimin centre and find <b>Identity Protection</b>: <br/>
<img src="https://i.imgur.com/owTU6yx.png" height="80%" width="80%"/>
<br />
<br />
Go to <b>user-risk policy</b>. Under <b>Assignments</b>, you can select from <b>All Users</b> or <b>Select individuals and groups</b>. You also have the option of excluding users from the policy:  <br/>
<img src="https://i.imgur.com/gj1MNYA.png" height="80%" width="80%"/>
<br />
<br />
Under <b>User risk</b>, you will select <b>Low and above</b>--This ensures that the policy triggers at the earliest sign of a compromised account, catching low, medium, and high risk detections: <br/>
<img src="https://i.imgur.com/uS3fNLv.png" height="80%" width="80%"/>
<br />
<br />
Under <b>Controls</b>, then <b>Acess</b>, select <b>Block access</b> then check the <b>Require password change</b> box and then select <b>Done</b>:  <br/>
<img src="https://i.imgur.com/ZO6muJ0.png" height="80%" width="80%"/>
<br />
<br />
Toggle to <b>Enabled</b> under <b>Policy encforcemnt</b> and then <b>Save</b>:  <br/>
<img src="https://i.imgur.com/ExVEJfT.png" height="80%" width="80%"/>
<br />
<br />
<h3>Enable sing-in risk policy</h3>
<p align="center">
Similar to <b>User risk</b>, under <b>Sign-in risk</b>, you can assign the policy to <b>All users</b> or to <b>individuals and groups</b>, and you can exclude users from the policy:  <br/>
<img src="https://i.imgur.com/UPjHcUm.png" height="80%" width="80%"/>
<br />
<br />
Under <b>sign-in risk</b>, select <b>Medium and above</b>--This minimizes False Positives:  <br/>
<img src="https://i.imgur.com/lAFwqMe.png" height="80%" width="80%"/>
<br />
<br />
Under <b>Controls</b>, then <b>Acess</b>, select <b>Block access</b> then check the <b>Require multifactor authentication</b> box and then select <b>Done</b>:  <br/>
<img src="https://imgur.com/PNeKxs0.png" height="80%" width="80%"/>
<br />
<br />
Toggle to <b>Enabled</b> under <b>Policy encforcemnt</b> and then <b>Save</b>:  <br/>
<img src="https://i.imgur.com/NJL9C9Z.png" height="80%" width="80%"/>
<br />
<br />
<h3>Enable Multifactor authentication registration policy</h3>
<p align="center">
Under <b>Assignments</b>, you can assign the policy to <b>All users</b> or to <b>individuals and groups</b>, and you can exclude users from the policy:  <br/>
<img src="https://i.imgur.com/WVXtpUR.png" height="80%" width="80%"/>
<br />
<br />
Toggle to <b>Enabled</b> under <b>Policy encforcemnt</b> and then <b>Save</b>:  <br/>
<img src="https://i.imgur.com/QNVFfHw.png" height="80%" width="80%"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
