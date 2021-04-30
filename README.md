- [**Open the Service Account GUI**](#open-the-service-account-gui)
- [**Group Managed Service Accounts (gMSA)**](#group-managed-service-accounts-gmsa)
  - [Add/Remove Group Managed Service Accounts](#addremove-group-managed-service-accounts)
    - [Create a New Group Managed Service Account](#create-a-new-group-managed-service-account)
    - [Remove a Group Managed Service Account](#remove-a-group-managed-service-account)
  - [Service Principal Names (SPNs)](#service-principal-names-spns)
    - [Assign a Service Principal Name (SPN) to a Group Managed Service Account](#assign-a-service-principal-name-spn-to-a-group-managed-service-account)
    - [Remove a Service Principal Name (SPN) to a Group Managed Service Account](#remove-a-service-principal-name-spn-to-a-group-managed-service-account)
  - [Principals Allowed to Retrieve Managed Password](#principals-allowed-to-retrieve-managed-password)
    - [Assign a Group Managed Service Account to a Computer or Group](#assign-a-group-managed-service-account-to-a-computer-or-group)
    - [Remove an Assigned Computer\Group from the Group Managed Service Account](#remove-an-assigned-computergroup-from-the-group-managed-service-account)
  - [Active Directory Group Membership](#active-directory-group-membership)
    - [Add a Group Managed Service Account to an AD Group](#add-a-group-managed-service-account-to-an-ad-group)
    - [Remove a Group Managed Service Account from an AD Group](#remove-a-group-managed-service-account-from-an-ad-group)
  - [Modify Group Managed Service Account (gMSA)](#modify-group-managed-service-account-gmsa)
    - [Modify a Group Managed Service Account Attributes](#modify-a-group-managed-service-account-attributes)
- [**Standard Service Accounts**](#standard-service-accounts)
  - [Add/Remove Standard Service Accounts](#addremove-standard-service-accounts)
    - [Create a New Standard Service Account](#create-a-new-standard-service-account)
    - [Remove a Standard Service Account](#remove-a-standard-service-account)
  - [Active Directory Group Membership](#active-directory-group-membership-1)
    - [Add a Standard Service Account to an AD Group](#add-a-standard-service-account-to-an-ad-group)
    - [Remove a Standard Service Account from an AD Group](#remove-a-standard-service-account-from-an-ad-group)
  - [Modify Standard Service Account](#modify-standard-service-account)
    - [Modify a Standard Service Account Attributes](#modify-a-standard-service-account-attributes)
  - [Account Migration](#account-migration)
    - [Create an identical gMSA from a Standard Service Account](#create-an-identical-gmsa-from-a-standard-service-account)

***

# **Open the Service Account GUI**

The Service Account GUI can be run as an elevated executable (preferred) or as a script. Below are the instructions to load as a script.

1. Log into a Domain Controller, in the domain where the service account will be created
2. Open PowerShell as Administrator
3. Navigate to the folder where the script is located
4. Run the following command:
 ```
 .\ServiceAccounts.ps1
 ```

***

# **Group Managed Service Accounts (gMSA)**

## Add/Remove Group Managed Service Accounts

### Create a New Group Managed Service Account

1. In the Service Account GUI
    1. Select the **Group Managed Service Accounts** tab
        1. Click the **Create New** button
2. In the **New Group Managed Service Account** window that appears
    1. Type the **Name** of the new account
        1. *NOTE: As you type, it is testing if an account exists with that name. If it does, it will recommend a new name.*
    2. Type the **Service Request #** from HPSM or Service Now
    3. Type the **Purpose** of the service account
    4. Select or type the **Functional Owner&#39;s Distribution Email Address**
    5. Optional Uncommon Options:
        1. Modify the User Logon name (sAMAccountName) if needed
        2. Modify the auto-populated **Description** if needed
        3.  **Enable** or Disable the account as required
        4. Modify the **Encryption Types** only if required
        5. Modify the **Container** to store the Managed Service Account
            1. This is not common
        6. Modify the **DNS Host Name** 
            1. This is not common
    6. Click **Create New Group Managed Service Account** button to create the account
        1. *NOTE: The button will be disabled if any field is not correct or needs attention.*



3. A success pop-up should appear, reminding you to run a command on the server that will be using the account
    1. Click **OK**



### Remove a Group Managed Service Account

1. In the Service Account GUI
    1. Select the **Group Managed Service Accounts** tab
2. Select the Account from the **Group Managed Service Account List**
3. Right click the Account, and click the **Remove** menu item
4. In the **Confirm** pop-up, type the name of the account exactly as shown
    1. Click **OK** to immediately (and irreversibly) delete the account

***

## Service Principal Names (SPNs)

### Assign a Service Principal Name (SPN) to a Group Managed Service Account

1. In the Service Account GUI
    1. Select the **Group Managed Service Accounts** tab
2. Select the Account from the **Group Managed Service Account List**
3. In the bottom right, select the **Service Principal Names (SPNs)** tab
4. Type the SPN that you would like to add, to the **Add SPN** textbox
    1. Click **Add** to add the SPN immediately to the account
5. Repeat to add additional SPNs



### Remove a Service Principal Name (SPN) to a Group Managed Service Account

1. In the Service Account GUI
    1. Select the **Group Managed Service Accounts** tab
2. Select the Account from the **Group Managed Service Account List**
3. In the bottom right, select the **Service Principal Names (SPNs)** tab
4. Select the SPN that you would like to remove
    1. Click the **Remove** button
    2. At the confirmation pop-up, select **Yes** to remove the SPN immediately

***

## Principals Allowed to Retrieve Managed Password

### Assign a Group Managed Service Account to a Computer or Group

1. In the Service Account GUI
    1. Select the **Group Managed Service Accounts** tab
2. Select the Account from the **Group Managed Service Account List**
3. In the bottom right, select the **Assigned Computers** tab
    1. Click the **Add** button
4. In the **AD Object Picker** pop up
    1. Select the **Type** (either Computer or Group)
    2. Type the **Name** (or partial name) of the Computer or Group
    3. Select the **Check Name** button
        1. In the table, select the Computer or Group to assign the gMSA to
        2. Click the **Select** button to immediately assign the Computer or Group to the gMSA


### Remove an Assigned Computer\Group from the Group Managed Service Account

1. In the Service Account GUI
    1. Select the **Group Managed Service Accounts** tab
2. Select the Account from the **Group Managed Service Account List**
3. In the bottom right, select the **Service Principal Names (SPNs)** tab
4. Select the SPN that you would like to remove
    1. Click the **Remove** button, to remove the assigned computer immediately

***

## Active Directory Group Membership

### Add a Group Managed Service Account to an AD Group

1. In the Service Account GUI
    1. Select the **Group Managed Service Accounts** tab
2. Select the Account from the **Group Managed Service Account List**
3. In the bottom right, select the **Member Of** tab
    1. Click Add
4. In the **AD Object Picker** pop up
    1. Type the **Name** (or partial name) of the Group
    2. Select the **Check Name** button
        1. In the table, select the Group to add the gMSA to
        2. Click the **Select** button to immediately add the gMSA to the selected group.


### Remove a Group Managed Service Account from an AD Group

1. In the Service Account GUI
    1. Select the **Group Managed Service Accounts** tab
2. Select the Account from the **Group Managed Service Account List**
3. In the bottom right, select the **Member Of** tab
4. Select the Group that you would like to remove
    1. Click the **Remove** button
    2. At the confirmation pop-up, select **Yes** to remove the gMSA from the AD Group immediately

***

## Modify Group Managed Service Account (gMSA)

### Modify a Group Managed Service Account Attributes

1. In the Service Account GUI
    1. Select the **Group Managed Service Accounts** tab
2. Select the Account from the **Group Managed Service Account List**
3. In the bottom left, modify the selected attribute(s)
    1. Any pending changes will change to a Green font
4. Click **Apply** , to apply the pending changes.
    1. *NOTE: If you add an Encryption Type other than AES256, you will be required to type in a phrase exactly (case-sensitive), to verify you want to select an unsafe encryption type*

***

# **Standard Service Accounts**

## Add/Remove Standard Service Accounts

### Create a New Standard Service Account

1. In the Service Account GUI
    1. Select the **Standard Service Accounts** tab
        1. Click the **Create New** button
2. In the **New Standard Service Account** window that appears
    1. Type the **Name** of the new account
        1. *NOTE: As you type, it is testing if an account exists with that name. If it does, it will recommend a new name.*
    2. Type the **Service Request #** from HPSM or Service Now
    3. Type the **Purpose** of the service account
    4. Either type in a **password** , or click the **Generate** button to create random 25 Character Password
        1. Save this password, as it will not be available again after account creation
    5. Select or type the **Functional Owner&#39;s Distribution Email Address**
    6. Optional Uncommon Options:
        1. Modify the User Logon name (sAMAccountName) if needed
        2. Modify the auto-populated **Description** if needed
        3.  **Enable** or Disable the account as required
            1. This option is only available if added a password above
        4. Modify the **Encryption Types** only if required
        5. Modify the password options and Account expiration as required
    7. Click **Create New Standard Service Account** button to create the account
        1. NOTE: The button will be disabled if any field is not correct or needs attention.
    8. A pop-up will appear to confirm you have saved the password (if created).
        1. Select **Yes** to continue; or select **No** to go back to save it
    9. A success pop-up should appear, reminding you to run a command on the server that will be using the account
        1. Click **OK**


### Remove a Standard Service Account

1. In the Service Account GUI
    1. Select the **Standard Service Accounts** tab
2. Select the Account from the **Standard Service Account List**
3. Right click the Account, and click the **Remove** menu item
4. In the **Confirm** pop-up, type the name of the account exactly as shown
    1. Click **OK** to immediately (and irreversibly) delete the account

***

## Active Directory Group Membership

### Add a Standard Service Account to an AD Group

1. In the Service Account GUI
    1. Select the **Standard Service Accounts** tab
2. Select the Account from the **Standard Service Account List**
3. In the bottom right, in the **Member Of** box
    1. Click Add
4. In the **AD Object Picker** pop up
    1. Type the **Name** (or partial name) of the Group
    2. Select the **Check Name** button
        1. In the table, select the Group to add the Account to
        2. Click the **Select** button to immediately add the Account to the selected group.

### Remove a Standard Service Account from an AD Group

1. In the Service Account GUI
    1. Select the **Standard Service Accounts** tab
2. Select the Account from the **Standard Service Account List**
3. In the bottom right, select the **Member Of** box
4. Select the Group that you would like to remove
    1. Click the **Remove** button
    2. At the confirmation pop-up, select **Yes** to remove the Account from the AD Group immediately

***

## Modify Standard Service Account

### Modify a Standard Service Account Attributes

1. In the Service Account GUI
    1. Select the **Standard Service Accounts** tab
2. Select the Account from the **Standard Service Account List**
3. In the bottom left, modify the selected attribute(s)
    1. Any pending changes will change to a Green font
4. Click **Apply** , to apply the pending changes.
    1. *NOTE: If you add an Encryption Type other than AES256, you will be required to type in a phrase exactly (case-sensitive), to verify you want to select an unsafe encryption type*

***

## Account Migration

### Create an identical gMSA from a Standard Service Account

1. In the Service Account GUI
    1. Select the **Standard Service Accounts** tab
2. Select the Account from the **Standard Service Account List**
3. Right click the Account, and click the **Create a gMSA from [accountname]** menu item
4. In the **New Group Managed Service Account** window that appears
    1. The Name field will be pre-populated with the selected account name
    2. Type the **Service Request #** from HPSM or Service Now
    3. Type the **Purpose** of the service account
    4. Select or type the **Functional Owner&#39;s Distribution Email Address**
    5. Optional Uncommon Options:
        1. Modify the User Logon name (sAMAccountName) if needed
        2. Modify the auto-populated **Description** if needed
        3.  **Enable** or Disable the account as required
        4. Modify the **Encryption Types** only if required
        5. Modify the **Container** to store the Managed Service Account
            1. This is not common
        6. Modify the **DNS Host Name**
            1. This is not common
    6. Click **Create New Group Managed Service Account** button to create the account
        1. NO*TE: The button will be disabled if any field is not correct or needs attention.*
    7. A success pop-up should appear, asking if you would like to add this gMSA account to the same groups that the Standard Service Account was in.
    8. Click **Yes** to add to the selected groups; Click **No** to not add to the selected Groups
    9. A success pop-up should appear, reminding you to run a command on the server that will be using the account
        1. Click **OK**