## Pre-Installation Instructions:

These steps must be completed before installing the unmanaged package (Estimated time: 20 minutes)

1. **Ensure the following licenses are installed in your Salesforce org:**
  - Health Cloud Service or Health Cloud CRM
  - Digital Engagement
  - Service Cloud Einstein or CRM Analytics
  - To confirm which licenses are installed in your org, please refer to this Help Article: [https://help.salesforce.com/s/articleView?id=sf.distribution\_assigning\_user\_licenses.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.distribution_assigning_user_licenses.htm&type=5)
2. **Enable "Send Email" and Allow Activities**
  - Setup \> Search for "Deliverability"
  - Select "Deliverability"
  - Set Send Email Access to "All Access"
  - Refer to this Help Article for more information: [https://help.salesforce.com/s/articleView?id=sf.data\_sandbox\_email\_deliverability.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.data_sandbox_email_deliverability.htm&type=5)
3. **Set the Organization-Wide Email Address**
  - Setup \> Email \> Organization-Wide Addresses
  - Enter the org address by clicking into Add a new User Selectable Organization-Wide Email Addresses.
  - Verify the email address set by opening the link sent to the email address.
4. **Enable Email-to-Case**
  - Refer to this Help Article for step-by-step instructions: [https://help.salesforce.com/s/articleView?id=sf.customizesupport\_enabling\_email\_to\_case.htm&language=en\_US](https://help.salesforce.com/s/articleView?id=sf.customizesupport_enabling_email_to_case.htm&language=en_US&r=https%3A%2F%2Fwww.google.com%2F&type=5#:~:text=From%20Setup%2C%20enter%20Email%2Dto,%2DCase%2C%20and%20click%20Save)
5. **Rename existing Log A Call Case Action**
  - Setup \> Object Manager \> Case
  - Navigate to the Actions section
  - Edit the Log A Call Action and rename the Name field.
6. **Enable Omni-Channel**
  - Use the Service Setup Flow for Omni-Channel. Refer to this Help Article for more information: [https://help.salesforce.com/s/articleView?id=sf.service\_presence\_intro.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.service_presence_intro.htm&type=5)
7. **Enable Knowledge**
  - Use the Service Setup Flow for Knowledge. Refer to this Help Article for more information: [https://help.salesforce.com/s/articleView?id=sf.service\_setup\_knowledge.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.service_setup_knowledge.htm&type=5)
  - Complete the setup steps listed here for Knowledge in the Contact Center for Health Cloud: [https://help.salesforce.com/s/articleView?id=sf.admin\_contact\_center\_enable\_users\_to\_create\_knowledge\_articles.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.admin_contact_center_enable_users_to_create_knowledge_articles.htm&type=5)
  - The Case Lightning Page in the Accelerator contains a Knowledge component. Enabling Knowledge is required to install the Accelerator. However, full implementation of Knowledge is not required. The customer may remove the component or reconfigure the Lightning Page as needed according to their business requirements.
8. **Enable CRM Analytics**
  - Ensure your Supervisor users are assigned the Service Cloud Einstein or CRM Analytics licenses
  - Enable Analytics in your org by following these steps: [https://help.salesforce.com/s/articleView?id=sf.mfg\_admin\_enable\_analytics.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.mfg_admin_enable_analytics.htm&type=5)
  - This is required in order to install the Accelerator as the Supervisor's Home Page in the package contains the Service Analytics dashboard powered by CRM Analytics/Service Cloud Einstein.
9. **Enable Messaging**
  - To support the post-case outgoing SMS Flow, enable Messaging according to this help article: [https://help.salesforce.com/s/articleView?id=sf.livemessage\_setup\_sms\_channels.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.livemessage_setup_sms_channels.htm&type=5)
  - ![](RackMultipart20230424-1-qcebko_html_168a58d6ac27c63e.png)
  - This step is required in order to install the Accelerator as the package contains an SMS messaging channel quick action that relies on the Digital Engagement SKU.

## Installation Steps:

These steps must be completed to install the unmanaged package of pre-built components for Contact Center

1. Use the Salesforce CLI utility to upload the assets in this GitHub repository into your Salesforce org: [https://github.com/salesforce/Accelerator-for-Patient-Services](https://github.com/salesforce/Accelerator-for-Patient-Services)
2. For guidance on how to use the Salesforce CLI, please refer to this documentation: [https://developer.salesforce.com/tools/sfdxcli](https://developer.salesforce.com/tools/sfdxcli)

OR

Navigate to the following URL: [https://login.salesforce.com/packaging/installPackage.apexp?p0=04t5f000000JkRb&isdtp=p1](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t5f000000JkRb&isdtp=p1)

## Post Installation Instructions:

These steps must be completed to enable the included components (Estimated time: 2-4 hours)

1. **Enable and Configure Contact Center for Health Cloud**
  1. Please follow the first 3 setup steps here: [https://help.salesforce.com/s/articleView?id=sf.admin\_contact\_center\_in\_health\_cloud.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.admin_contact_center_in_health_cloud.htm&type=5)
    - Enable Admin Settings to Use Contact Center
    - Assign Permission Sets and Permission Set Licenses for Contact Center Users
    - Set Up Standard Object Permissions for the Contact Center User
  2. To add the Accelerator to the Contact Center App, please follow the following steps.
    1. Activate the "Patient Console - Contact Center" Person Account Lightning App Page - _ **NOTE: This replaces the steps titled "Configure the Person Account Page Layout for Contact Center"** _
      - In Setup \> Lightning App Builder \> Edit "Patient Console - Contact Center"
      - Add the following components to the lightning app based on your business requirements. For more information about these components, please refer to this help article: [https://help.salesforce.com/s/articleView?id=sf.admin\_contact\_center\_explore\_the\_components.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.admin_contact_center_explore_the_components.htm&type=5)
        1. Knowledge
        2. Enhanced Timeline
        3. Action Launcher
        4. Advanced Patient Card
        5. Profile Card
        6. Member Plan Card
        7. Record Alerts
      - Click Save and then click **Activation**.
      - In the **Activation** : Account Record Page window, go to the App Default tab.
      - Click Assign as **App Default**.
      - In the Select Apps window, click **Contact Center**.
      - Click Next, then Next, and **Save**.
    2. Activate the Case Lightning App Page for the Contact Center
      - In Setup \> Lightning App Builder \> Edit the CaseDefault\_Record\_Page app
      - Click on **Activation** \> go to the App Default tab.
      - Click Assign as **App Default**.
      - In the Select Apps window, click **Contact Center**.
      - Click Next, then Next, and **Save**.
    3. Configure Record Alerts by following the steps outlined in this help artice: [https://help.salesforce.com/s/articleView?id=sf.common\_set\_up\_record\_alerts.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.common_set_up_record_alerts.htm&type=5)

1. **Navigate to the Health Cloud Admin app**
  - Click on Patient Card Configurations
  - Delete the following Configuration records:
    1. Motivation
    2. Conditions
    3. Insurance Plans
    4. Medications
  - Please refer to Page 40 of this guide for the steps involved in configuring additional fields for the Patient Card: [https://blog.bessereau.eu/assets/pdfs/salesforce\_health\_cloud\_impl\_guide.pdf](https://blog.bessereau.eu/assets/pdfs/salesforce_health_cloud_impl_guide.pdf)
2. **Configure which Subtabs open for the Patient Person Account**
  - Please refer to Page 45 of this guide to configure which subtabs open by default for a Person account: [https://blog.bessereau.eu/assets/pdfs/salesforce\_health\_cloud\_impl\_guide.pdf](https://blog.bessereau.eu/assets/pdfs/salesforce_health_cloud_impl_guide.pdf)
3. **Configure Case Reason and Case Type Picklists**
  - Setup \> Object Manager \> Case Object
  - Navigate to the Fields & Relationships screen
    1. Click on "Case Reason"
    2. Under "Case Reason Picklist Values", add or remove values in order to align to your organization's business process
    3. Save and return to the Fields & Relationships screen
    4. Click on "Type"
    5. Under "Type Picklist Values", add or remove values in order to align to your organization's business process
4. **Reconfigure and share the Patient Services Analytics App**
  - App Launcher \> Analytics Studio
  - Select the Patient Services Analytics app
  - Click on "Reconfigure App" in the top right hand corner of the page
  - Select Basic and follow the prompts to reconfigure the app
  - You may need to Share the App with the specified supervisor users.
    1. To do so, from the Analytics Studio home page, select the drop-down for the Patient Services Analytics app \> Share.
    2. Select the desired set of users or group.
    3. If the dashboard is not shared properly, the supervisor user will see an error message on their home page "Dashboard not found: Service\_Overview"
5. **Configure Omni-Channel**
  - Follow these steps to configure your team's Case Queues and Omni-Channel Settings:
    1. Service Setup \> Service Setup Assistant
    2. Follow the prompts to complete the setup steps:

![](RackMultipart20230424-1-qcebko_html_82b521963f00573a.png)

    1. Follow the instructions in this Help Article to configure Omni-Channel and Case Queues to align to Scheduling, Clinical, and General case types: [https://help.salesforce.com/s/articleView?id=sf.console\_lex\_service\_setup\_omnichannel.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.console_lex_service_setup_omnichannel.htm&type=5)
    2. Assign your agents based on their skillset to the Scheduling, Clinical, and General case queues.
1. **Configure Profiles**
  - Create a new Profile for your Patient Services **Agents** which aligns to the Salesforce License Type.
  - Configure Object Access for the Task Object such that the Default Record Type is **not** the Master Record Type.

![](RackMultipart20230424-1-qcebko_html_4122a6e64c231c58.png)

  - Ensure to align the Profile to these components:

| **Component Type** | **Component Name** |
| --- | --- |
| Lightning App | Contact Center - Set as Default |
| Default Home Page - Patient Services App | Patient Services Agent Home Page |
| Case Record Types | Clinical, General, Scheduling |
| Case Page Layouts | Clinical, General, Scheduling |
| Task Record Types | Clinical, General, Scheduling |
| Task Page Layout | Task Layout - Contact Center |
| PersonAccount Page Layout | Patient Layout - Contact Center |
| Dashboard Folder | Patient Services |
| Report Folder | Patient Services |

  1. Create a new Profile for your Patient Services **Supervisors**. You may choose to Clone the Patient Services Agent profile. Additionally, please add the Omni Supervisor app to the Patient Services Navigation Items for the supervisor.
  - Configure Object Access for the Task Object such that the Default Record Type is **not** the Master Record Type.

![](RackMultipart20230424-1-qcebko_html_4122a6e64c231c58.png)

  - Ensure to align the Profile to these components:

| **Component Type** | **Component Name** |
| --- | --- |
| Lightning App | Contact Center - Set as Default |
| Default Home Page - Patient Services App | Patient\_Services\_Supervisor\_Home\_Page |
| Case Record Types | Clinical, General, Scheduling |
| Case Page Layouts | Clinical, General, Scheduling |
| Task Record Types | Clinical, General, Scheduling |
| Task Page Layout | Task Layout - Contact Center |
| PersonAccount Page Layout | Patient Layout - Contact Center |
| Dashboard Folder | Patient Services |
| Report Folder | Patient Services |

1. **Upload CDC approved Care Barrier Types and Care Barrier Intervention Types**
  - Download the SDoH files in the GitHub repository above
  - Ensure that your administrator user has the appropriate Health Cloud Permission Set License and Permission Set Assignments and CRUD access to the Care Barrier Type and Intervention Type objects. Otherwise, these objects will not show up as available to select in Dataloader.io.
  - Upsert the Care Barrier Types and Intervention Types into your org using DataLoader.
  - For instructions on how to operate DataLoader, refer to this Help Article: [https://developer.salesforce.com/docs/atlas.en-us.dataLoader.meta/dataLoader/data\_loader\_using.htm](https://developer.salesforce.com/docs/atlas.en-us.dataLoader.meta/dataLoader/data_loader_using.htm)
  - Verify that the Care Barrier Types and Intervention Types are present in your Salesforce org:
    1. App Launcher \> Care Barrier Types
    2. App Launcher \> Intervention Types
  - For additional configuration options, please refer to these Help Articles:
    1. [https://developer.salesforce.com/docs/atlas.en-us.236.0.health\_cloud.meta/health\_cloud/landing\_social\_determinants.htm](https://developer.salesforce.com/docs/atlas.en-us.236.0.health_cloud.meta/health_cloud/landing_social_determinants.htm)
2. **Configure Patient Survey**
  - Leverage the default Customer Satisfaction survey in Health Cloud to configure it based on your organization's needs.
    1. Launch the latest version of the survey and configure according to your business process.
    2. Refer to this Help Article for additional information regarding Surveys: [https://developer.salesforce.com/docs/atlas.en-us.health\_cloud.meta/health\_cloud/surveys\_overview.htm](https://developer.salesforce.com/docs/atlas.en-us.health_cloud.meta/health_cloud/surveys_overview.htm)
  - Alternatively, you may leverage the included survey samples in the accelerator as inspiration.
3. **Configure Macro to Close Case and Send Survey**
  - Download the following Macro .csv files from the GitHub repository above:
    1. macro\_1 - Case Close Macro Instructions.csv
    2. macro\_1 - Case Close Macro.csv
  - Use DataLoader to upload these files to your Salesforce org in this order:
    1. Macro
      1. After the Macro is imported, please note down the new Macro record ID if it has changed.
    2. Macro Instructions
      1. Before importing, open up the macro\_1 - Case Close Macro Instructions.csv file and ensure the "MACROID" column values are equal to the Macro record ID from the previous step.
  - For instructions on how to operate DataLoader, refer to this Help Article: [https://developer.salesforce.com/docs/atlas.en-us.dataLoader.meta/dataLoader/data\_loader\_using.htm](https://developer.salesforce.com/docs/atlas.en-us.dataLoader.meta/dataLoader/data_loader_using.htm)
  - After importing the Macro, refer to this Help Article to configure the Macro further: [https://help.salesforce.com/s/articleView?id=sf.macros\_def.htm&type=5](https://help.salesforce.com/s/articleView?id=sf.macros_def.htm&type=5)

