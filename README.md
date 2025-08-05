<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>

This this is a continuation of [Configuring-Active-Directory-within-Azure-VMs](https://github.com/zachwiseit/Configuring-Active-Directory-within-Azure-VMs/blob/main/README.md)


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop .<br />
- Active Directory Domain Services
- PowerShell
- Windows App(macOS)

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)
- macOS Sonama 14.6.1

<h2>Deployment and Configuration Steps</h2>
1 The first portion of this will be Setting up the remote desktop for non-administrative users on Client-1 
  First things first log into client-1 as mydomain.com\jane_admin
<p>
<p>
<img <img width="1440" alt="CPS_1" src="https://github.com/user-attachments/assets/3f41c845-ee8b-4596-880f-4fd6a6c47f5a" />
<p>
3 Once you are logged in we are going to open system properties. 
  Right click start and click "System".
<p>
<img <img width="1440" alt="CPS_3" src="https://github.com/user-attachments/assets/7ed0d897-96e4-4081-ba64-98333d3da7e0" />
</p>
<p>
4 On the far right click "Remote desktop". 
<p>
<img <img width="1440" alt="CPS_4" src="https://github.com/user-attachments/assets/247093a2-40cc-412b-a02e-0d2b04433c4a" />
</p>
<p>
5 Now we need tp allow “domain users” access to remote desktop.
  Under User accounts click "Select users that can remotely access this PC.
<p>
<img <img width="1440" alt="CPS_5" src="https://github.com/user-attachments/assets/582e139d-d838-4f8a-b4e1-45187ceb891d" />
</p>
<p>
6 Click "Add".
<p>
<img <img width="1440" alt="CPS_6" src="https://github.com/user-attachments/assets/c5f2bffb-bbde-42dc-809d-e84804cc6082" />
</p>
<p>
7 In the "Enter the object names to select" text box type domain users and click "Ceheck Names". Then click "OK".
<p>
<img <img width="1440" alt="CPS_7" src="https://github.com/user-attachments/assets/7aae5948-2363-4997-a2ee-34dbf75ee827" />
</p>
<p>
8 Click "OK". 
  Now effectlivley all domain users will be able to log into this computer. 
<p>
<img <img width="1440" alt="CPS_8" src="https://github.com/user-attachments/assets/60286562-732a-4fe1-ae8a-b1a0e5a8d3b2" />
</p>
<p>
9 Now we are going to use power shell to create multiple users inside active directory. 
  Log back into dc-1 if you are not already. 
  In the search bar type powershell.
<p>
<img <img width="1440" alt="CPS_9" src="https://github.com/user-attachments/assets/4b692f6f-256f-462c-8ac2-b6aac1f13e7c" />
</p>
<p>
10 In Apps right click "Windows Powershell ISE" and clcik "Run as administrator". 
<p>
<img <img width="1440" alt="CPS_10" src="https://github.com/user-attachments/assets/694d9cdf-35ab-4a11-9df0-8e27ce754b1c" />
</p>
<p>
11 Click "Yes".
<p>
<img <img width="1440" alt="CPS_11" src="https://github.com/user-attachments/assets/62820482-74dc-4473-8f03-c2af2c83ba9a" />
</p>
<p>
12 Now go to this link https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1 and copy the script 
   Copy the Raw file. 
<p>
<img <img width="1440" alt="CPS_12" src="https://github.com/user-attachments/assets/1609f6b7-3b0c-4e90-af29-c748f8fbe93f" />
</p>
<p>
13 Back in Powershell click "New Script". 
<p>
<img <img width="1440" alt="CPS_13" src="https://github.com/user-attachments/assets/ee007a9b-94dc-43c1-9f21-a4aa2696449b" />
</p>
<p>
15 Hit CTRL S and save it to the desktop. Name it something like "create-users" anc click "Save". 
<p>
<img <img width="1440" alt="CPS_15" src="https://github.com/user-attachments/assets/11075ba1-0146-4da9-8b7b-46af829174e2" />
</p>
<p>
16Now paste that script in the open area. 
<p>
<img <img width="1440" alt="CPS_16" src="https://github.com/user-attachments/assets/0fa586ec-5fe0-46b6-87f7-ce408937029b" />
</p>
<p>
18 At the top click "Run Script". 
<p>
<img <img width="1440" alt="CPS_18" src="https://github.com/user-attachments/assets/ef3b2143-3c0a-421e-8d37-afe5705f34e0" />
</p>
<p>
19 mark the chekc box and click "OK".
<p>
<img <img width="1440" alt="CPS_19" src="https://github.com/user-attachments/assets/4a42171d-9f2b-42ce-9879-4e8ed84be483" />
</p>
<p>
20 Then it will begin to create multiple users (10,000 to be exact). 
<p>
<img <img width="1440" alt="CPS_20" src="https://github.com/user-attachments/assets/4acca608-321f-49c2-9966-5c1b8d388253" />
</p>
<p>
22 If you open up Active, Right click _EMPLOYEES, and click "Refresh" you will see a list of generated names. 
   Now pick a a user (does not matte which one) and try to log in as that user. 
<p>
<img <img width="1440" alt="CPS_22" src="https://github.com/user-attachments/assets/aa137118-facb-4e75-a4dd-ef1890ce5695" />
</p>
<p>
23 Now sign out. 
<p>
<img <img width="1440" alt="CPS_23" src="https://github.com/user-attachments/assets/5e4be5ff-c0a6-43b6-a1fc-bb65b874d84d" />
</p>
<p>
24 Log into client-1 and put in mydomain.com\user you chose. 
   All the users passwords by defult is "Password1". 
   click "Continue".
<p>
<img <img width="1440" alt="CPS_24" src="https://github.com/user-attachments/assets/1d4c8b0d-6bc5-453c-a1c7-d6a47782f6ec" />
</p>
<p>
25 Now it will begin the process of starting up a new user. 
<p>
<img <img width="1440" alt="CPS_25" src="https://github.com/user-attachments/assets/8f30b6ad-72d1-42d3-a079-27a41ce7c48e" />
</p>
<p>
27 Once everything is loaded. Search Command Prompt and open it. 
<p>
<img <img width="1440" alt="CPS_27" src="https://github.com/user-attachments/assets/0fa7fb4a-1039-44ac-8153-bc01f1d63e7c" />
</p>
<p>
28 It will show that you have a local profile on this computer. 
   At the bottom click file explorer. 
<p>
<img <img width="1440" alt="CPS_28" src="https://github.com/user-attachments/assets/35766363-fe56-4808-8967-79b77df23656" />
</p>
<p>
30 Go to "This PC" and click the C drive. 
<p>
<img <img width="1440" alt="CPS_30" src="https://github.com/user-attachments/assets/d688d79b-3fcd-4bef-a9d5-ee5129200003" />
</p>
<p>
31 Click "Users".
<p>
<img <img width="1440" alt="CPS_31" src="https://github.com/user-attachments/assets/f470e8b3-7f00-4474-9182-d5f7f6ac4bde" />
</p>
<p>
32 Here you can see both this users profile and the jane_admin profile as well. 
<p>
<img <img width="1440" alt="CPS_32" src="https://github.com/user-attachments/assets/73539b05-fa17-499b-bf86-b6b00fc7210e" />
</p>
<p>
33 Now sign out as that user. 
<p>
<img <img width="1440" alt="CPS_33" src="https://github.com/user-attachments/assets/bd281c4c-0ca3-4882-82ee-f26bc4ca6561" />
</p>
<p>
34 Back to the power shell script it will still be making users. However plenty have been create for what we need. 
   You can either let it go till all 10,000 are created or at the top of the powershell page click the red box to Stop Operations.
<p>
<img <img width="1440" alt="CPS_34" src="https://github.com/user-attachments/assets/ee61c433-29d5-4dc7-890e-15192a96918d" />
</p>
<p>
36 Now we are going to go through the process of changes a users password after too many log in attempts. 
   Go back into Active drectory and pick a random user. 
   (Make sure you are logged out of client 1.)
<p>
<img <img width="1440" alt="CPS_36" src="https://github.com/user-attachments/assets/27f59375-ab09-44af-ae76-e7367b687c6a" />
</p>
<p>
38 After you choose your users we need to set up the account lockout policy in Active directory. 
   Right click start and click "Run".
<p>
<img <img width="1440" alt="CPS_38" src="https://github.com/user-attachments/assets/8e2f6137-e1f2-40ed-8881-08f486411386" />
</p>
<p>
39 In run type "gpmc.msc" and click "OK".
<p>
<img <img width="1440" alt="CPS_39" src="https://github.com/user-attachments/assets/03cf0812-5fdc-4e16-81cf-ed85e90dc9cf" />
</p>
<p>
40 Doing that will bring up the Group Policy Management 
<p> 
<img <img width="1440" alt="CPS_40" src="https://github.com/user-attachments/assets/90c719c0-3c8c-4554-aaea-433bfe4216c5" />
</p>
<p>
42 Right click "Default Domain Policy" and click "Edit". 
<p>
<img <img width="1440" alt="CPS_42" src="https://github.com/user-attachments/assets/d3aa7400-ecd8-4894-b86a-246c473bda7e" />
</p>
<p>
44 CLick the Drop arrow for Windows Settings > Security Settings then click "Account policies". 
   Next click "Account lockout duration".
<p>
<img <img width="1440" alt="CPS_44" src="https://github.com/user-attachments/assets/b2397a49-cad3-4d6a-8963-38cc76e8bab7" />
</p>
<p>
46 Check the box for Define this policy setting. Then change the Account is locked out for: to 30 minutes and click "OK". 
<p>
<img <img width="1440" alt="CPS_46" src="https://github.com/user-attachments/assets/6e8a7124-73c5-4cdc-a9d9-14c713be8980" />
</p>
<p>
47 Click "OK" again. 
<p>
<img <img width="1440" alt="CPS_47" src="https://github.com/user-attachments/assets/66420754-3ecf-4131-b90b-caee9e69687d" />
</p>
<p>
48 You can see now that the lockout duration has been changed. The account lockout threshold has also automatically updated to five invalid logon attempts. 
<p>
<img <img width="1440" alt="CPS_48" src="https://github.com/user-attachments/assets/20ae4c31-d0f0-46e9-a0b2-929f642a70b0" />
</p>
<p>
49 With that changed our policy is good and you can close the Group policy Management Editor. 
<p>
<img <img width="1440" alt="CPS_49" src="https://github.com/user-attachments/assets/347ea8f6-64c7-45f6-a33e-91a837ea9fc5" />
</p>
<p>
50 Another way to check the policy is go to Settings. 
   Click "Close".
<p>
<img <img width="1440" alt="CPS_50" src="https://github.com/user-attachments/assets/b92f1359-5d37-4c96-b2e2-4ba116b56793" />
</p>
<p>
51 IF you scroll down to Account Polcies/Account Lockout Policy you can see the the changes we made. 
<p>
<img <img width="1440" alt="CPS_51" src="https://github.com/user-attachments/assets/f9c9e95a-09ed-4628-83f4-1ded1047b7c1" />
</p>
<p>
53 Now we are going to sign back into client-1 as Jane_admin to force the policy to refresh. 
<p>
<img <img width="1440" alt="CPS_53" src="https://github.com/user-attachments/assets/8f7bdd24-11f0-4f56-a756-114f3c1cc21b" />
</p>
<p>
54 Now the policy will reset over time but we are going to do that ourselves. 
   Search Command Prompt in the search bar and click it. 
<p>
<img <img width="1440" alt="CPS_54" src="https://github.com/user-attachments/assets/9d0e2b96-135d-4c4f-873a-869719f576da" />
</p>
<p>
55 In the command line type "gpupdate /force" and press enter. 
<p>
<img <img width="1440" alt="CPS_55" src="https://github.com/user-attachments/assets/8df163e4-26c2-4c22-a3f8-a17ad2bda491" />
</p>
<p>
57 After the update was successfully complete sign out of client-1.
<p>
<img <img width="1440" alt="CPS_57" src="https://github.com/user-attachments/assets/abac77c3-2047-4b46-b806-f0db5ce5dc98" />
</p>
<p>
59 Now try to sign in as the user you chose with the wrong password. Do this until locked out. 
<p>
<img <img width="1440" alt="CPS_59" src="https://github.com/user-attachments/assets/3778416e-6755-4e32-949d-955cb61f0192" />
</p>
<p>
60 Afte renough attempts you will be notified that the users account has been locked out due to too many sign in attempts. 
   Click "Close". 
<p>
<img <img width="1440" alt="CPS_60" src="https://github.com/user-attachments/assets/13cd8092-cc9c-494e-a011-6f77664cccb2" />
</p>
<p>
61 Go back to dc-1, Active Directory Users and Computers, Right click mydomain.com, and click "Find". 
<p>
<img <img width="1440" alt="CPS_61" src="https://github.com/user-attachments/assets/78c4bee2-259e-4d79-abc1-f180ced43af0" />
</p>
<p>
62 Put in the user you chose and click "Find".
<p>
<img <img width="1440" alt="CPS_62" src="https://github.com/user-attachments/assets/9e8d1b8a-52d5-4841-a4fb-8860db38704b" />
</p>
<p>
63 In the resultes you will see that users account.
   Double click the user. 
<p>
<img <img width="1440" alt="CPS_63" src="https://github.com/user-attachments/assets/d0523180-7d46-48de-b694-aa6b66e42982" />
</p>
<p>
64 Click "Account". 
<p>
<img <img width="1440" alt="CPS_64" src="https://github.com/user-attachments/assets/16daa11d-99c2-45d9-a5f5-2c01c5ffcf38" />
</p>
<p>
66 Check the box next to "Unlock account" and click "Apply". 
<p>
<img <img width="1440" alt="CPS_66" src="https://github.com/user-attachments/assets/636fb351-25e4-4fff-b759-09778ca26062" />
</p>
<p>
68 Go back and sign into client-1 as that user with the correct password. 
<p>
<img <img width="1440" alt="CPS_68" src="https://github.com/user-attachments/assets/4f48a391-18d5-48c1-bdd2-7213ad8b04e5" />
</p>
<p>
69 Now it is unlocked and you can get back into client-1 as that user. 
<p>
<img <img width="1440" alt="CPS_69" src="https://github.com/user-attachments/assets/93a8ac80-a02e-4e58-8aec-f64aa539319a" />
</p>
<p>
70 Another way to check that you are on that users account is go to powershell. 
<p>
<img <img width="1440" alt="CPS_70" src="https://github.com/user-attachments/assets/fc20e585-044e-465c-a3cb-a6bc18b078d6" />
</p>
<p>
71 It will state it at the top but you can also type "whoami" and click enter. 
<p>
<img <img width="1440" alt="CPS_71" src="https://github.com/user-attachments/assets/2047d8c2-9701-4bdb-8715-5d0a44d2914e" />
</p>
<p>
72 This will tell you what user is signed in. 
<p>
<img <img width="1440" alt="CPS_72" src="https://github.com/user-attachments/assets/e5613c2d-246f-4ad8-9a91-49381be98ded" />
</p>
<p> 
73 Back in dc-1 we are going to go through the process of enabling/disabling accounts.
   You can use a different user or the same one. Search for them again, right click the user, and click "Disable Account".
<p>
<img <img width="1440" alt="CPS_73" src="https://github.com/user-attachments/assets/43c18e9b-3c40-4800-871f-ec0ef1bfcb20" />
</p>
<p>
74 Click "OK" and now the account has been disabled. 
<p>
<img <img width="1440" alt="CPS_74" src="https://github.com/user-attachments/assets/976af94f-a79f-4b9e-931c-cb0f0caaebca" />
</p>
<p>
76 IF you click "Find Now" again the user will have a little down arrow next to their icon showing the account is disabled. 
<p>
<img <img width="1440" alt="CPS_76" src="https://github.com/user-attachments/assets/1cd57c6e-3b7f-45a4-99cc-cbda2c8a4476" />
</p>
<p>
77 Next we are going to go back to client-1 and sign out. 
<p>
<img <img width="1440" alt="CPS_77" src="https://github.com/user-attachments/assets/4fb5d70f-f209-404a-90a1-e93b2c8e338e" />
</p>
<p>
79 Then try to log back in as the disabled account. 
<p>
<img <img width="1440" alt="CPS_79" src="https://github.com/user-attachments/assets/7b5e0316-a23c-41d8-83e8-1df7de3ed7ac" />
</p>
<p>
80 After you click continue this notification will pop up stating that this account is disabled. 
   Click "Close".
<p>
<img <img width="1440" alt="CPS_80" src="https://github.com/user-attachments/assets/7467705e-9fe4-4e9c-b89c-697be9c35663" />
</p>
<p>
81 Now we are going to go back into dc-1 and enable the account. 
   Its the same process, right click the user and click "Enable Account".
<p>
<img <img width="1440" alt="CPS_81" src="https://github.com/user-attachments/assets/02898217-a2fb-4204-afc2-f1f20d2fc70a" />
</p>
<p>
83 Click "Find Now" and after it refresshes the little down arrow will be gone and this user will be active again. 
<p>
<img <img width="1440" alt="CPS_83" src="https://github.com/user-attachments/assets/75b002b5-937d-4869-984b-401d9825f31c" />
</p>
<p>
84 Now we are going to go back to client-1 to verify that the account is active. 
   Sign back in as that user. 
<p>
<img <img width="1440" alt="CPS_84" src="https://github.com/user-attachments/assets/879b54ca-5ac8-4b5f-a153-7e506df7d290" />
</p>
<p>
85 With the account reactivated you will be signed back into client-1.
<p>
<img <img width="1440" alt="CPS_85" src="https://github.com/user-attachments/assets/2a3b68ce-40d7-4267-9541-ea6311261bbf" />
</p>
<p>
86 Lastly we are going to go through the steps to check and observe the logs in the Domain Controller. 
   Back in dc-1 search for evetnvwr.msc and click it. 
<p>
<img <img width="1440" alt="CPS_86" src="https://github.com/user-attachments/assets/9fd499ac-f1be-459c-a540-3bfa072526ae" />
</p>
<p>
87 On the left expand Windows logs rhen click "Security". 
<p>
<img <img width="1440" alt="CPS_87" src="https://github.com/user-attachments/assets/2fc1eb44-72b9-4d13-8230-b18039c6647c" />
</p>
<p>
88 There are alot of events to go through so we are going to search for specific ones. 
   Right click "Security" and click "Find".
<p>
<img <img width="1440" alt="CPS_88" src="https://github.com/user-attachments/assets/7f0bae50-37c3-4d33-856e-077f1e14629e" />
</p>
<p>
89 In the search bar type in the user account that you have been signing in with. Then click "Find Next".
<p>
<img <img width="1440" alt="CPS_89" src="https://github.com/user-attachments/assets/495c116b-b3de-4ed2-9b8b-f3db8358be3d" />
</p>
<p>
90 This will show the most reacent log for that user. Click "Find Next" again will continue to go down the list. 
<p>
<img <img width="1440" alt="CPS_90" src="https://github.com/user-attachments/assets/cde0d1cf-668b-48b3-8b4e-8277d66c4285" />
</p>
<p>
92 Each event is going to be different with different information. Lets try and find those failed log in attempts. 
<p>
<img <img width="1440" alt="CPS_92" src="https://github.com/user-attachments/assets/6d74dd54-448e-4c9f-aa33-31127d69a0ac" />
</p>
<p>
96 Go back to the start bar and search evetnvwr.msc. Then Run as administrator. 
<p>
<img <img width="1440" alt="CPS_96" src="https://github.com/user-attachments/assets/1a89e77f-f001-4a5f-8bbf-7ebfdbaf1231" />
</p>
<p>
97 Now sign in as your admin user, and click "Yes". 
<p>
<img <img width="1440" alt="CPS_97" src="https://github.com/user-attachments/assets/e37d03f4-dbc9-443e-834e-d94566c9e42a" />
</p>
<p>
98 Go back into the security logs like before. 
<p>
<img <img width="1440" alt="CPS_98" src="https://github.com/user-attachments/assets/f77f8202-37ec-4a9b-9afb-bf760699460e" />
</p>
<p>
99 After it loads you can see the audit failures from our log in attempts.
   If you scroll down you can see additional details like the user, ip address, and much more. 
<p>
<img <img width="1440" alt="CPS_99" src="https://github.com/user-attachments/assets/4f8df4b1-9bb7-4348-9590-0eaf1564172f" />
</p>
<p>
