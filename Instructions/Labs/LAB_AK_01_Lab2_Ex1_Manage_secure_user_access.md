# Learning Path 1 - Lab 2 - Exercise 1 - Manage secure user access 

Organizations must ensure that access to their company data on Microsoft 365 is always secure. Microsoft 365 - and int turn, Copilot for Microsoft 365 - often displays sensitive and confidential data, including emails, documents, customer information, and intellectual property. Unauthorized access to Microsoft 365 can lead to data breaches, identity theft, and other malicious activities. By securing user access, organizations can prevent unauthorized individuals from accessing and potentially misusing or leaking company data when working in Microsoft 365 and Copilot for Microsoft 365.

In the following lab exercise, you will continue in your role as Holly Dickson, Adatum's new Microsoft 365 Administrator. You will perform several user management functions to prepare Adatum for its upcoming Copilot for Microsoft 365 deployment. You will begin by creating a Microsoft 365 user account for Holly, who will be assigned the Microsoft 365 Global Administrator role. 

**Note:** The VM environment provided by your lab hosting provider comes with over 20 existing Microsoft 365 user accounts, as well as a large number of existing on-premises user accounts. Several of the existing Microsoft 365 user accounts will be used throughout the labs in this course. Even though the MOD Administrator account has been created by your lab hosting provider, you will still create Holly Dickson's user account, since having more than one user who's assigned the Microsoft 365 Global Administrator role is a best practice. It will also provide you with the experience of creating a Microsoft 365 user account in case you're not familiar with the process.

Holly has then been asked by Adatum’s CTO to deploy Microsoft Entra Multifactor Authentication (MFA) and Microsoft Entra Smart Lockout. These features will help strengthen password management throughout the organization in preparation for Copilot for Microsoft 365. For Smart Lockout, you will deploy it using Group Policy Management. 


### Task 1 - Create a User Account for Adatum's Microsoft 365 Administrator

Holly Dickson is Adatum’s new Microsoft 365 Administrator. Since a Microsoft 365 user account has not been set up for her, she initially signed into Microsoft 365 as the MOD Administrator account (the default Global administrator) in the previous lab. In this task, you will continue to be logged in as the MOD Administrator, during which you will create a Microsoft 365 user account for Holly. You will also assign the Microsoft 365 Global Administrator role to Holly's account. This role will provide Holly with the permissions needed to perform all administrative functions within Microsoft 365. Following this task, you will log in using Holly's new account and you will perform all remaining labs using Holly's persona. 

**License Note:** Before creating Holly's account, you will first verify the number of available licenses. In doing so, you will note that while your lab tenant provides 20 Microsoft 365 E5 (no Teams) licenses and 20 Microsoft Teams Enterprise licenses, all those licenses have already been assigned to the existing user accounts created by your lab hosting provider. As such, you must first unassign one of each license from an existing user so that you can assign them to Holly.

**Important:** As a best practice in your real-world deployment, you should always write down the credentials of the first Global administrator account (in this lab, it's the MOD Administrator account, whose username is admin@xxxxxZZZZZZ.onmicrosoft.com, where xxxxxZZZZZZ is the tenant prefix assigned by your lab hosting provider). You should store away this account information for security reasons. **This account should be a NON-personalized identity** that owns the highest privileges possible in a tenant. It should **not** be MFA activated because it is not personalized. Because the username and password for this first Global admin account are typically shared among several users, this account is a perfect target for attacks; therefore, it's always recommended that organizations create personalized service admin accounts (for example, an Exchange admin, SharePoint admin, and so on) and keep as few personal Global admins as possible. For those personal Global admins that you do create in your real-world deployment, they should each be mapped to a single user (such as Holly Dickson), and they should each have Microsoft Entra Multi-Factor Authentication (MFA) enforced.

1. On the **LON-CL1** VM, the **Microsoft 365 admin center** should still be open in your Microsoft Edge browser from the prior lab exercise. You should be signed into Microsoft 365 as the **MOD Administrator**. 

2. Since you are adding a new user, you should begin by checking license availability before adding the user account. In the **Microsoft 365 admin center** navigation pane, select **Billing** to expand the Billing group, and then select **Licenses**. 

3. On the **Licenses** page, the **Subscriptions** tab is displayed by default. In the list of subscriptions, note the **Microsoft 365 E5 (no Teams)** and **Microsoft Teams Enterprise** subscriptions don't have any available licenses. Your lab tenant provides 20 licenses for each subscription, but all 40 licenses have been assigned. Since you must assign Holly both a **Microsoft 365 E5 (no Teams)** license and a **Microsoft Teams Enterprise** license, you must first unassign the licenses from an existing user account to make them available for Holly. 

4. In the **Microsoft 365 admin center** navigation pane, select **Users** and then select **Active users**. In the **Active users** list, you will see the list of existing user accounts that were created by your lab hosting provider. Since Christie Cline will be moving to a new role in the company and will no longer be part of the Microsoft 365 pilot project, you will unassign the **Microsoft 365 E5 (no Teams)** and **Microsoft Teams Enterprise** licenses from her account so that you can reassign them to Holly Dickson's new account.

5. On the **Active users** page, in the list of users, select **Christie Cline** (select Christie's hyperlinked name and not the check box next to her name).

6. In the **Christie Cline** pane that appears, the **Account** tab is displayed by default. Select the **Licenses and apps** tab. Under **Licenses (2)**, select the check boxes next to **Microsoft 365 E5 (no Teams)** and **Microsoft Teams Enterprise** to clear them, and then select **Save changes**. Once the changes are saved, close the **Christie Cline** pane. 

7. You're now ready to create a user account for Holly Dickson, who is Adatum's new Microsoft 365 Administrator. In doing so, you will assign Holly the Microsoft 365 Global Administrator role, which gives Holly global access to most management features and data across Microsoft online services. You will also assign Holly the two licenses that you just unassigned from Christie Cline. <br/>

	In the **Active Users** window, select the **Add a user** option that appears on the menu bar above the list of active users. This starts the **Add a user** wizard.

8. In the **Set up the basics** page of the **Add a user** wizard, enter the following information:

	- First name: **Holly**

	- Last name: **Dickson** 

	- Display name: When you tab into this field, **Holly Dickson** will appear.

	- Username: **Holly** <br/>
	
		‎**IMPORTANT:** To the right of the **Username** field is the domain field. It will be prefilled with the **xxxxxZZZZZZ.onmicrosoft.com** cloud domain (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider).<br/>
	
	- Clear (uncheck) the **Automatically create a password** check box, which will display a new field for entering an administrator-defined password.

	- Enter the New Administrative Password in the **Password** field that appears 

	- Clear (uncheck) the **Require this user to change their password when they first sign in** check box 

9. Select **Next**. If a **Save password** dialog box appears towards the top of the screen, select **Never**.

10. In the **Assign product licenses** page, enter the following information: <br/>

	- Select location: **United States**

	- Licenses: Under the **Assign user a product license** option, select the **Microsoft 365 E5 (no Teams)** and **Microsoft Teams Enterprise** check boxes

11. Select **Next**.

12. In the **Optional settings** page, select the drop-down arrow to the right of **Roles**. 

13. In the **Roles** section, select the **Admin center access** option. By selecting this option, the most commonly used Microsoft 365 administrator roles are enabled below it.  <br/>

	**Note:** All the admin roles will be displayed if you select **Show all by category**, which appears after the last common role. For Holly, you don't need to view all the admin roles by category, since Holly will be assigned the Global Administrator role that appears in the list of commonly used roles.

14. Select the **Global Administrator** check box. <br/>

	**Note:** A warning message will be displayed indicating that Adatum already has 7 Global admins. In a normal environment, this would be excessive and not recommended. For the purposes of this lab, the lab hosting provider assigned the Global admin role to the MOD Administrator and six other user accounts, which is not something you would normally see in a real-world deployment. However, for the purpose of this lab in your fictitious Adatum lab environment, ignore this message. **That being said, the best practice guideline that you should follow is to have from two to four Global Administrators in your real-world Microsoft 365 deployments.** 

15. Select **Next**.

16. On the **Review and finish** window, review your selections. If anything must be changed, select the appropriate **Edit** link and make the necessary changes. Otherwise, if everything is correct, select **Finish adding**. 

17. On the **Holly Dickson added to active users** page, under the **User details** section, select the **Show** option to verify Holly's password is the same **Administrative Password** provided by your lab hosting provider for the tenant admin account (i.e. the MOD Administrator account).  <br/>

	**Note:** If you accidentally entered a different password, then once you return to the **Active Users** page, you will need to select the **Reset a password** icon (the key icon that appears when you hover over Holly's account) to change her password to the correct value.

18. Select **Close.**

19. Remain logged into the Client 1 VM (LON-CL1) with the Microsoft 365 admin center open in your browser for the next task.


### Task 2 – Update the Microsoft 365 pilot project group

After completing the previous task, you should still be signed into the **Microsoft 365 admin center** as the **MOD Administrator** account. In this task, you will begin implementing Adatum’s Microsoft 365 pilot project as Holly Dickson, Adatum’s new Microsoft 365 Administrator. Therefore, you will begin this task by logging out of Microsoft 365 as the MOD Administrator and you will log back in as Holly. 

In a previous task, you created a Microsoft 365 group for the members of Adatum's pilot project team so that you could create a custom theme for that group. In this task, you will add Holly to this group. 

1. On the LON-CL1 VM, the **Microsoft 365 admin center** should still be open in your Microsoft Edge browser from the prior task. You should be signed into Microsoft 365 as the **MOD Administrator**. <br/>

	On the **Microsoft 365 admin center** tab, in the upper-right corner of the screen, note that it displays the MOD Administrator's name and megaphone icon. The name is displayed because of the custom theme that you created in the prior lab exercise that was associated with a group of Microsoft 365 pilot project users that included the MOD Administrator. Keep this in mind once you log back in as Holly Dickson. <br/>

	Select the user icon or the circle with the "MA" initials for the **MOD Administrator** in the upper right corner of your browser. In the **MOD Administrator** window that appears, select **Sign out.** <br/>
	
	**Important:** When signing out of one user account and signing in as another, you should close all your browser tabs except for the **Sign out** tab. This is a best practice that helps to avoid any confusion by closing the windows associated with the prior user. Once you're signed out of the MOD Administrator account, take a moment and close all other browser tabs except for the **Sign out** tab. 
	
2. In your Microsoft Edge browser, in the **Sign out** tab, enter the following URL in the address bar to sign back into Microsoft 365: **https://portal.office.com**. 

3. In the **Pick an account** window, only the MOD Administrator's tenant admin account (the admin@xxxxxZZZZZZ.onmicrosoft.com account) that you just signed out from appears. Select **Use another account**. 

4. In the **Sign in** window, enter **Holly@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider). Select **Next**.

5. In the **Enter password** window, enter the New Administrative Password that you assigned to Holly's account and then select **Sign in**. 

6. If a **Stay signed in?** dialog box appears, select the **Don’t show this again** check box and then select **Yes.** 

7. If a **Welcome to Microsoft 365** dialog box appears in the middle of the screen, there's no option to close it. Instead, to the right of the window, select the forward arrow icon (**>**) two times and then select the check mark icon to advance through the slides in this messaging window. 

8. If a **Create with Microsoft 365** window appears, select the **X** in the top corner of the window to close it. 

9. The **Welcome to Microsoft 365** page appears in your Edge browser in the **Home | Microsoft 365** tab. This is Holly's Microsoft 365 home page. Note that Holly's initials appear in the upper-right corner of the screen; however, Holly's name is not displayed. This is because Holly's account did not exist at the time you added the Microsoft 365 pilot project users to the group that was associated with the custom theme in the prior lab exercise. Since Holly wants to see her name at the top of each Microsoft 365 window when she's logged into the system, she first wants to add her account to the group of Microsoft 365 pilot project users. <br>

	In the column of application icons that appears in the navigation pane on the side of the screen, select **Admin**. This opens the **Microsoft 365 admin center** in a new browser tab. 

10. In the **Microsoft 365 admin center**, select **Teams & groups** in the navigation pane, and then under it, select **Active teams & groups**. 

11. In the **Active teams and groups** page, there's a tab for viewing each of the group types. The **Teams & Microsoft 365 groups** tab is displayed by default. In this tab, select **M365 pilot project**.

12. In the **M365 pilot project** pane that appears, the **General** tab is displayed by default. Select the **Membership** tab.

13. In the **Membership** tab, the **Owners** sub-tab is displayed by default in the navigation pane that appears on the side of the pane. Select the **Members** sub-tab that appears below it.

14. In the **Members** sub-tab, select **+Add members**.

15. In the **Add group members to M365 pilot project** pane that appears, select inside the **Search by name or email address** field. In the list of users that appears, scroll down and select **Holly Dickson**. Select the **Add (1)** button, and then close the **Add group members to M365 pilot project** pane once Holly is added to the group.

16. Remain logged into LON-CL1 with the **Microsoft 365 admin center** open in your browser for the next task.


### Task 3: Create a Conditional Access policy to implement MFA

As your training indicated, there are three ways to implement MFA - with Conditional Access policies, with security defaults, and with legacy per-user MFA (not recommended for larger organizations). In this exercise, you'll enable MFA through a Conditional Access policy, which is the method that Microsoft recommends. Adatum has directed Holly to enable MFA for all its Microsoft 365 users - both internal and external. However, for the purpose of testing Adatum's Microsoft 365 pilot project implementation, Holly wants to exclude the members of the M365 pilot project group from having to use MFA to sign in. Once the pilot project is complete, Holly will update the policy by removing the exclusion of this group from the MFA requirement. The policy will also include two other requirements. It will require MFA for all cloud apps, and it will require MFA even if a user signs in from a trusted location. 

1. On the LON-CL1 VM, the **Microsoft 365 admin center** should still be open in your Microsoft Edge browser from the prior task. You should be signed into Microsoft 365 as **Holly Dickson**.
   
2. In the **Microsoft 365 admin center**, under the **Admin centers** section in the navigation pane, select **Identity**. Doing so opens the Microsoft Entra admin center in a new browser tab. If a **Pick an account** window appears, select **Holly Dickson's account**.

3. In the **Microsoft Entra admin center**, select **Protection** in the navigation pane, and then select **Conditional Access**.

4. On the **Conditional Access | Overview** page, select **Policies** in the middle navigation pane.

5. On the **Conditional Access | Policies** page, on the menu bar at the top of the page, select **+New policy**.

6. On the **New Conditional Access policy** window, enter **MFA for all Microsoft 365 users** in the **Name** field.

7. You will begin by defining the MFA requirement for users. Under the **Users** group, select **0 users and groups selected**. Doing so displays two tabs - **Include** and **Exclude**.

8. Under the **Include** tab, select **All users**. Note the warning message that appears. You will address this in the next two steps.

9. Select the **Exclude** tab. To avoid system lockout, as the prior warning message indicated, you want to exclude your Global administrators - in this case, Holly. Holly also wants to exclude the other Microsoft 365 pilot project group members for the sake of expediency when testing. Once Microsoft 365 goes live at Adatum, Holly will remove the pilot project group from the Exclude list in this Conditional Access policy and simply exclude herself, the MOD Administrator, and a few other Global admins. But for now, Holly wants to exclude the entire pilot project group. <br/>

	To do so, select the **Users and groups** check box. 

10. In the **Select excluded users and groups** window that appears, you want to select the Microsoft 365 pilot project group. The **All** tab is displayed by default. To quickly find the pilot project group, select the **Groups** tab. In the list of active groups, select the check box next to the **M365 pilot project** group, and then select the **Select** button at the bottom of the window. Back on the **New Conditional Access policy** window, note the message that appears under the **Users** section. 

11. You will now define the MFA requirement for all cloud apps. Under the **Target resources** section, select **No target resources selected**. Doing so displays two tabs - **Include** and **Exclude**.

12. Select the **Select what this policy applies to** drop-down field to see the various options in the drop-down menu. Select **Cloud apps**. 

13. Under the **Include** tab, note that the default setting is **None**. If you did not change this setting, then no cloud apps would require MFA - and that includes Microsoft 365. So even if you created this policy and selected the option to require MFA for all users, but you left this **Target resources** setting to **None**, then any user signing into Microsoft 365 would not have to use MFA. <br/>

	Under the **Include** tab, select the **Select apps** option. Doing so displays two sections - **Edit filter** and **Select**. Under the **Select** section, select **None**. 

14. In the **Select Cloud apps** pane that appears, scroll down through the list of apps to see all the different apps that you could require MFA for. **Do NOT select any of the apps.** We're having you scroll through this list just to get a feel for how granular you can get when requiring MFA should you decide to limit MFA to certain apps in your real-world deployments.  <br/>

	For Adatum, Holly wants to require MFA for all cloud apps, which is typically a more common business scenario than selecting specific apps. Under the **Include** tab, select the **All cloud apps** option. Adatum will not exclude any cloud apps from MFA authentication. You can select the **Exclude** tab if you want to see the options it provides. It works basically the same as the **Include** tab. You can view this tab, but do NOT select any cloud apps for exclusion. 

15. Finally, you will define the MFA requirement for all user sign-in locations. In some scenarios, organizations may only require MFA if a user signs-in from an untrusted location. However, Adatum wants to require MFA for all included users, regardless of the location from where they sign in. <br/>

	Under **Conditions**, select **0 conditions selected**. Doing so displays a list of potential conditions the policy will check for. For this lab exercise, under the **Locations** condition, select **Not configured**. Doing so displays a **Configure** toggle switch and two tabs - **Include** and **Exclude**. Both tabs are currently disabled.

16. Set the **Configure** toggle switch to **Yes**, which enables the two tabs. 

17. Under the **Include** tab, verify **Any network or location** is selected (select it if necessary). Select the **Exclude** tab. If your organization recognizes specific IP addresses or ranges of addresses as "trusted", you can exclude the MFA requirement if a user signs in from one of those locations. However, Adatum wants to require MFA for all user sign-in attempts, regardless of their location. This will include both internal and external user sign-ins. Verify the **Selected networks and locations** option is selected, and under the **Select** section, verify it says **None**. By not specifying any selected locations, this setting ensures that no locations are excluded from MFA. 

18. Under the **Access controls** section, under the **Grant** group, select **0 controls selected**. Doing so displays a **Grant** pane.

19. In the **Grant** pane that appears, verify the **Grant access** option is selected (select it if necessary). Note all the access controls that are available that can be enabled with this policy. This policy will only require MFA, so select the **Require multifactor authentication** check box. Select the **Select** button at the bottom of the **Grant** pane, which closes the pane. 

20. At the bottom of the **New Conditional Access policy** window, in the **Enable policy** field, select **On**.

21. Note the warning message and options that appear at the bottom of the page that warn you not to lock yourself out. Select the option **I understand that my account will be impacted by this policy. Proceed anyway.** In fact, Holly won't be impacted since she's a member of the M365 pilot project group that is excluded from this policy.

22. Select the **Create** button to create the policy.

23. On the **Conditional Access | Policies** window that appears, verify the **MFA for all Microsoft 365 users** policy appears and that its **State** is set to **On**.

24. Remain logged into LON-CL1 with all your Microsoft Edge browser tabs open for the next task.


### Task 4: Test MFA for both an included and excluded user

To test the Conditional Access policy that you just created, you will sign-out of Microsoft 365 as Holly, and then you'll sign back in as Adele Vance. Adele is not a member of the M365 pilot project group, so Microsoft Entra should require that she use MFA when signing in. Once you sign-in as Adele and verify that MFA works, you will sign-out as Adele and then sign back in as Holly. Since Holly is a member of the M365 pilot project group that was excluded from using MFA in the Conditional Access policy, you should not have to use MFA when signing in as Holly. Similarly, you won't have to use MFA when you sign in as the various members of the M365 pilot project group in the remaining labs in this course.

**Important:** To implement MFA, you must use your mobile phone to receive a verification code so that you can enter it into your tenant as a second form of authentication. If you do not have a phone, you can still test your Conditional Access policy. For students without a phone, when you sign in as Adele Vance, the system will require you to sign in with a second form of authentication. At that point, you can simply cancel out of your sign-in and then sign back in as Holly, who will not require MFA. While you will not complete the MFA sign-in for Adele, you can still verify that the system forces you to use it when attempting to sign-in.

1. On the LON-CL1 VM, the **Microsoft 365 admin center** should still be open in your Microsoft Edge browser from the prior task. You should be signed into Microsoft 365 as **Holly Dickson**. You will begin by signing out of Microsoft 365. On the **Microsoft 365 admin center** tab, select Holly's name in the upper right corner of your browser. In the **Holly Dickson** window that appears, select **Sign out.** 
	
2. Once you are signed out of Microsoft 365 as Holly, close your browser session to clear your cache. Then select the **Edge** icon on your taskbar to open a new browser session. In your browser, go to the **Microsoft 365 Home** page by entering the following URL in the address bar: **https://portal.office.com/** 

3. In the **Pick an account** window that appears, select **Use another account**. 

4. In the **Sign in** window, enter **AdeleV@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) and then select **Next**. In the **Enter password** window, enter the **User Password** provided by your lab hosting provider and select **Sign in**.

5. Because MFA is enabled for all users except for the M365 pilot project group members (of which, Adele is not a member), a **More information required** window appears. Select **Next**. This returns the **Microsoft Authenticator** page, which is the starting point for signing in with MFA. <br/>

	**Important:** If you do not have a phone, then this is as far as you can go when attempting to sign-in as Adele. Even though you can't complete the sign-in, you have verified that the first part of your Conditional Access policy is working, since it requires Adele to sign-in using MFA. At this point, skip to step #18 so that you can sign back in as Holly.

6. On the **Microsoft Authenticator** page that appears, you can download this mobile app or use a different method for MFA verification. For the purposes of this lab, we recommend that you use your mobile phone so that you do not have to take time installing the Microsoft Authenticator app that you may not use again after this training class. Select the **I want to set up a different method** option at the bottom of the page (**Important:** Do NOT confuse this link with the **I want to use a different authenticator app** that appears above it). 

7. In the **Choose a different method** dialog box that appears, select the drop-down arrow in the **Which method would you like to use?** field, select **Phone**, and then select **Confirm**. 

8. In the **Phone** window that appears, under **What phone number would you like to use?** field, select your country or region, and then in the field next to it, enter your phone number (in the format **nnn-nnn-nnnn**). Verify the **Receive a code** option is selected and then select **Next**.

9. Retrieve the verification code from the text message that is sent to your phone.

10. In the **Phone** window, enter the 6-digit verification code in the code field and then select **Next**. When the **Phone** window displays a message indicating your phone was registered successfully, select **Next**.

11. On the **Success!** page, select **Done**.

12. Microsoft has implemented a new security policy in the trial tenants that are used in its training labs. All of the predefined test user accounts are configured so that students must change their initial password at their next sign-in. You experienced this earlier when you signed into Microsoft 365 as the MOD Administrator in the first lab exercise. You must do so now with Adele. <br>

	In the **Update your password** window that appears, enter the **User Password** provided by your lab hosting provider in the **Current password** field. Then in the **New password** and **Confirm password** fields, enter the New User Password that you defined for all test users at the start of the lab. Select **Sign in**.

13. If a **Stay signed in?** dialog box appears, select the **Don’t show this again** check box and then select **Yes.** 

14. If a **Welcome to Microsoft 365** dialog box appears, select the right arrow twice and then select the check mark.

15. If a **Create with Microsoft 365** window appears, select the **X** to close it.

16. On the **Welcome to Microsoft 365** page, select the **Word** icon that appears in the column of app icons on the left-side of the screen. This opens **Microsoft Word Online**. Doing so validates that you can access a Microsoft 365 app after signing in using MFA.  <br/>

	**Important:** You have now verified that the first part of the Conditional Access policy that you created works. The policy requires that a user who is not a member of the Microsoft 365 pilot project team must sign-in using MFA. You verified this works when you signed in as Adele. You will now sign out as Adele and sign back in as Holly, during which you will verify that the second part of the Conditional Access policy also works. You should NOT have to use MFA when signing in as Holly, since she's a member of the M365 pilot project group, which is excluded from the MFA requirement in the Conditional Access policy.

17. On the **Microsoft 365 admin center** tab, select the icon for Adele's account in the upper right corner of your browser. In the **Adele Vance** window that appears, select **Sign out.** <br/>
	
18. Close your browser session to clear your cache. Select the **Edge** icon on your taskbar to open a new browser session. In your browser go to the **Microsoft 365 Home** page by entering the following URL in the address bar: **https://portal.office.com/** 

19. In the **Pick an account** window, select **Holly@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) and then select **Next**. In the **Enter password** window, enter the new Administrative Password that you defined for all test users at the start of the lab and later assigned to Holly's account. Select **Sign in**.

20. Because MFA is required for all users except for the M365 pilot project team members (of which, Holly is a member), MFA will not be required. Since MFA is not required, the system displays the **Microsoft 365 Home** page in the **Home | Microsoft 365** tab. 

21. If a **Welcome to Microsoft 365** dialog box appears, select the right arrow twice and then select the check mark.

22. If a **Create with Microsoft 365** window appears, select the **X** to close it.

23. On the **Welcome to Microsoft 365** page, select the **Admin** icon in the side pane to navigate to the **Microsoft 365 admin center**. <br/>

	**Important:** You have now verified that the second part of the Conditional Access policy that you created works. The policy excludes members of the Microsoft 365 pilot project group from signing-in using MFA. Holly is a member of this group, and she did not have to sign in using MFA.

24. Remain signed into LON-CL1 with the **Microsoft 365 admin center** open in your browser.


### Task 5: Deploy Microsoft Entra Smart Lockout

Adatum’s CTO has asked you to deploy Microsoft Entra Smart Lockout, which assists in locking out bad actors who are trying to guess your users’ passwords or use brute-force methods to get admitted into your network. Smart Lockout can recognize sign-ins coming from valid users and treat them differently than sign-ins from attackers and other unknown sources. 

The CTO is anxious to implement Smart Lockout because it will lock out the attackers while letting Adatum’s users continue to access their accounts and be productive. The CTO has asked Holly to configure Smart Lockout so that users can’t use the same password more than once, and they can’t use passwords that are considered too simplistic or common. 

**Note:** You can maintain Account Lockout Policy settings in both the Group Policy Management Editor and in Microsoft Entra through its Smart Lockout feature. This lab task shows you how to access each method, although you will only update the Smart Lockout settings in Microsoft Entra. You must use the company's domain controller (LON-DC1) to access the Group Policy Management Editor. 

1. In the prior tasks, you worked in LON-CL1. In this task, you will be working from Adatum's domain controller, LON-DC1. <br/>

	Switch to **LON-DC1**.

2. On **LON-DC1**, you must select **Ctrl+Alt+Delete** to log in (your instructor will guide you on how to find this option in your VM environment). Log into LON-DC1 as the local Adatum administrator account that was created by your lab hosting provider (**Administrator**) with the password **Pa55w.rd**.

3. On LON-DC1, **Server Manager** automatically starts at boot-up. In **Server Manager**, select **Tools** in the upper-right menu bar, and in the drop-down menu, select **Group Policy Management.** Maximize the **Group Policy Management** window that appears.

4. You want to edit the group policy that includes your organization's account lockout policy. If necessary, in the root console tree in the side pane, expand **Forest:Adatum.com**, then expand **Domains**, and then expand **Adatum.com**.  <br/>

	‎Under **Adatum.com**, right-click on **Default Domain Policy** and then select **Edit** in the menu.

5. Maximize the **Group Policy Management Editor** window that appears.

6. In the **Default Domain Policy** tree in the side pane, under **Computer Configuration**, expand **Policies**, expand **Windows Settings**, expand **Security Settings**, and then expand **Account Policies.**

7. In the **Account Policies** folder, select **Account Lockout Policy**.

8. As you can see in the pane that appears, none of the smart lockout parameters have been defined. Instead of maintaining these lockout parameters in the Group Policy Management Editor, you're instead going to use the Microsoft Entra admin center. While you can use the Group Policy Management Editor, this method is typically used in on-premises Active Directory environments. We showed you this editor so that you could see this alternative. However, for organizations that strictly use cloud-based services like Microsoft 365, or who find using the Microsoft Entra admin center much more user-friendly than accessing the Group Policy Management Editor, using the **Microsoft Entra admin center** to assign corresponding values in the Entra ID context is preferrable. <br/>  

	Also keep in mind that the lockout behavior and customization options differ between the two methods. With the Group Policy Management Editor, you have more granular control over policy settings, including Account Lockout Threshold, Lockout Duration, and Reset Account Lockout Counter After. However, using this method requires familiarity with Group Policy and Active Directory administration. Conversely, the Account Lockout Policy in Microsoft Entra can't be customized as extensively. However, it’s easier to use, even though it lacks some of the fine-tuning options available in Group Policy. <br/>

	For Adatum, Holly has chosen to use the Microsoft Entra admin center to configure the company's Account Lockout policy. ‎On the taskbar at the bottom of your screen, select the **Microsoft Edge** icon. If necessary, maximize your browser window when it opens.

9. In your Edge browser, go to the **Microsoft 365 Home** page by entering the following URL in the address bar: **https://portal.office.com** 

10. In the **Sign in** dialog box, you must sign in as Holly Dickson. Enter **Holly@xxxxxZZZZZZ.onmicrosoft.com**, where xxxxxZZZZZZ is the tenant prefix assigned by your lab hosting provider. Select **Next**. <br/>

11. In the **Enter password** dialog box, enter the New Administrative Password that you assigned to Holly's account and then select **Sign in**. 

12. On the **Stay signed in?** dialog box, select the **Don’t show this again** check box and then select **Yes.** On the **Save password** dialog box that appears, select **Never**.

13. If a **Welcome to Microsoft 365** dialog box appears in the middle of the screen, there's no option to close it. Instead, to the right of the window, select the forward arrow icon (**>**) two times and then select the check mark icon to advance through the slides in this messaging window. 

14. If a **Find more apps** window or a **Create with Microsoft 365** window appears, select the **X** in the upper top corner of the windows to close them. 

15. On the **Welcome to Microsoft 365** page, in the list of application icons that appear in the side window pane, select **Admin**; this opens the **Microsoft 365 admin center** in a new browser tab. 

16. In the **Microsoft 365 admin center**, select **Show all** in the navigation pane. Under **Admin centers**, select **Identity**, which displays the **Microsoft Entra admin center** in a new tab.

17. In the **Microsoft Entra admin center**, select **Protection** in the navigation pane, and then select **Authentication methods**.

18. In the **Authentication methods | Policies** page, in the middle pane under the **Manage** section, select **Password protection.**

19. In the **Authentication methods | Password protection** window, in the detail pane on the right, enter the following information:

	- In the **Custom smart lockout** section:

		- **Lockout threshold:** this field indicates how many failed sign-ins are allowed on an account before its first lockout. The default is 10. For testing purposes, Adatum has requested that you set this to **3**.

		- **Lockout duration in seconds:** This is the length in seconds of each lockout. The default is 60 seconds (one minute). Adatum has requested that you change this to **90** seconds.

	- In the **Custom banned passwords** section:

		- **Enforce custom list**: select **Yes**

		- **Custom banned password list:** Enter the following values (press Enter after entering each value so that each value is on a separate line):

			- **Password01**

			- **F00tball01**

			- **Se@Hawks1**

			- **Never4get!!**

	- In the **Mode** section, select **Enforced**

20. Select **Save** on the menu bar at the top of the page.

21. You should now test the banned password functionality. Select Holly Dickson's user icon in the upper right corner of the screen, and in the menu that appears select **View account**. 

22. In the **My account** window that appears, in the **Password** tile, select **CHANGE PASSWORD**.

23. A new tab will open displaying the **Change password** window. In the **Old password** field, enter Holly's existing password, which is the New Administrative Password. <br/>

	Enter **Never4get!!** in the **Create new password** and **Confirm new password** fields, and then select **Submit**. Note the error message that you receive.

24. In your browser, close the **Change password** tab. 

25. You're now going to test the lockout threshold functionality. You're going to do so using Patti Fernandez's account. Select Holly Dickson's user icon in the upper right corner of the screen, and in the menu that appears select **Sign out**.  

26. Once you are signed out as Holly, the **Pick an account** window will appear in the **Sign in to Microsoft Entra** tab. As a best practice when signing out from a Microsoft online service as one user and signing back in as another, close all your browser tabs except for the **Sign out** or **Sign in** tab. In this case, close the other tabs now and leave the **Sign in** tab open.  <br/>

	In the **Pick an account** window, select **Use another account**. 

27. In the **Sign in** window, enter **pattif@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix assigned to you by your lab hosting provider), and then select **Next**. 

28. On the **Enter password** window, enter any random mix of letters and numbers and then select **Sign in**. Note the invalid password error message that appears. 

	Repeat this step 2 more times. 
	
	Since you set the **Lockout threshold** to **3**, you should receive an error message indicating that this account is locked after the third failed sign-in attempt. <br/>

	**Note:** If you do not receive this lockout message after the third attempt, then the system has not yet finished propagating this lockout threshold change throughout the service. It may take several minutes for the change to take effect. Wait a few minutes and then sign-in again with a bogus password. Testing of this lab has seen varying results. The change sometimes propagates almost immediately so that you get locked out after the third sign-in attempt. Other times it has taken anywhere from 5 to 10 minutes before the lockout message is displayed. Continue this process until you receive the lockout message, at which point Patti's account will be temporarily locked to prevent unauthorized access.

29. You will be prohibited from logging in again as Patti until after the **90 second lockout duration** that you set earlier. <br/>

	Once you've been locked out, wait 90 seconds and then sign back in as **pattif@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix assigned to you by your lab hosting provider). In the **Password** field, enter Patti's password, which is the **User Password** provided by your lab hosting provider. 
 
30. As you recall, all the predefined test user accounts in your trial tenant are configured so that you must change their initial password at their next sign-in. When the **Update your password** window appears, that is verification that your sign-in attempt using Patti's actual password was successful. <br>

	**Note:** You do NOT need to complete the sign-in process for Patti, since this is your last lab exercise using the LON-DC1 domain controller. You can close all applications on LON-DC1.
 
# Proceed to Lab 2 - Exercise 2
