
<h1>Entra ID monitoring with splunk</h1>


<h2>Description</h2>

A walk-through of common attacks techniques targeting Entra ID identities and what they leave behind in logs and to hunt for them in a SIEM environment like Splunk.
<br />


<h3>Password-based attacks</h3>
Attackers acquire credentials from credential dumping sites, and many of these credentials are tied to active corporate accounts where users have reused passwords. Once attackers has a list of credentials they attempt to gain access without needing to touch the target's network perimeter. A successful login is identical to a legitimate one, no exploit, no malware, no network anomalies. So, to catch such attacks we have to hunt for them and analyse the logs.

<b>Password spraying(T1110.003) :</b> Attackers use a small list of commonly used passwords against many different accounts, this is done so as not to trigger the lockout threshold.
<br />
<br />

<p align="center">
Sign-in to Microsoft Entra adimin centre and find <b>Identity Protection</b>: <br/>
<img src="https://i.imgur.com/bDSjgFz.png" height="80%" width="80%"/>
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
