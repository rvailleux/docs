# 

##  

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/prerequis.png) | You need to have completed the installation on a [sandbox](install-deploy-on-a-sandbox-environment.md)or on a [production](install-deploy-on-your-production-environment.md) environment before configuring your environment. |
| :--- | :--- |

In this guide, you will:
* [Assign permission sets to end users](configure-your-salesforce-environment.md#h2_2046225501)
* [Enable video call statistics](configure-your-salesforce-environment.md#h1_permission_stats)
* [Enable Trusted URL](configure-your-salesforce-environment.md#h2__252222865)
* [Add the Apizee component on Object Layout](configure-your-salesforce-environment.md#h2_2130507011)
* [Assign a layout for Contact Object and Case Object (optional)](configure-your-salesforce-environment.md#h2_1398860885)
* [Apizee Connector for Salesforce Setup](configure-your-salesforce-environment.md#h2_382852360)

##  Assign permission sets to end users

2 permission sets are included in package to set accessibility of Apizee package features:

* **Apizee Admin**: this permission set grants access to all Apizee app features, including the **Apizee Configuration** tab.
* **Apizee User**: this permission set grants access to Apizee app features, without the access to the **Apizee Configuration** tab. This can be assigned to end users.

Let's assign permission sets to end users:

1. Connect to the target environment as a **System Administrator.**
2. Open the **Setup** console.
3. Navigate to **Users** &gt; **Permission Sets.** ![A screenshot of a computer
Description automatically generated](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0010.png)
4. Click **Apizee Admin** permission set. 
 
 ![A screenshot of a computer
Description automatically generated](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0011.png)
5. Click **Manage Assignments.**
6. Click **Add Assignment.** ![Une image contenant texte, capture d’écran, ligne, Police  Description générée automatiquement](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0012.png)
7. Check the checkboxes in front of users you want the permission set to be assigned to.
8. Click **Next.**
9. Click **Assign.**

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | The permission sets are now assigneed to the users |
| :--- | :--- |

## Enable video call statistics

| ![Information](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/info.png) | For some reason, the Apizee User permission set can't be installed with read/write access to Tasks&gt;Type field.<br><br>Follow the steps below to fix this anomaly. |
| --- | --- |

1. Open Salesforce and go to the **Permission Sets** section.
2. Select the **Apizee User** permission set.
3. Check if the **Task object** has read and write access to the **Type field**.
4. If the access is not available:
    1. Click **Clone** to make a copy of the Apizee User permission set.
    2. Open the new permission set.
    3. Go to **Object Settings** &gt; **Task**.
    4. Edit the settings and add read and write access to the **Type field**.
    5. Save the changes.
5. Assign the new permission set to the applicable users.

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | *The users have access to the Type field in the Task object.* |
| --- | --- |

## Enable Trusted URL 

1. Open the **Setup** console.
2. Navigate to **Security &gt; Trusted URLs.**
3. Click **New Trusted URL**. ![Une image contenant texte, capture d’écran, logiciel, Icône d’ordinateur  Description générée automatiquement](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0026.png)
4. Fill in the information as below:

    * API Name: **Apizee**
    * URL: **\*.apizee.com**
    * Active: **checked**
5. Activate the following **CSP Directives:**
    * frame-src (iframe content)
    * img-src (images)
    * media-src (audio and video)

 ![Une image contenant texte, Police, nombre, capture d’écran  Description générée automatiquement](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0028.png)
6. Click **Save**
7. Click **New Trusted URL**   ![Une image contenant texte, capture d’écran, logiciel, Icône d’ordinateur  Description générée automatiquement](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0026.png)
8. Fill in the information as below:
 ![A screenshot of a computer  Description automatically generated](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0029.png)

    * API Name: **ApizeeCloudURL**
    * URL:**\*.apirtc.com**
    * Active: **checked**
9. Activate the following **CSP Directives** 

    * frame-src (iframe content)
    * img-src (images)
    * media-src (audio and video)

 ![Une image contenant texte, Police, nombre, capture d’écran  Description générée automatiquement](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0028.png)
10. Click **Save**

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | The URLs are now declared as Trusted URLs |
| :--- | :--- |

## 

| Add the Apizee component on Object Layout | Add the Apizee component on Object Layout 
<br>If you want to add component on an existing Layout page instead of using the default layout (see above).<br><ol> <li>Open<b> </b>a <b>Case </b>or <b>Contact </b>record detail. </li> <li>Click <b>Settings </b>menu (circle in red below). <div> <img src="../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0020.png" alt="Une image contenant texte, capture d’écran, logiciel, Icône d’ordinateur  Description générée automatiquement" style="max-width: 602px; width: 100%; height: auto;" loading="lazy"> </div> <br> </li> <li>Click <b>Edit Page.</b> <div> <img src="../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0021.png" alt="Une image contenant texte, capture d’écran, Police, nombre  Description générée automatiquement" style="max-width: 159px; width: 100%; height: auto;" loading="lazy"> </div> </li> <li> In the next window, scroll down the <b>Components list</b> in the left panel until you see the <b>webAgent</b> component. <div> <img src="../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0022.png" alt="Une image contenant texte, capture d’écran, logiciel, Icône d’ordinateur  Description générée automatiquement" style="max-width: 602px; width: 100%; height: auto;" loading="lazy"> </div> </li> <li>Drag the <b>webAgent</b> and drop it on one of the sections in the page layout. <br>In the following example, the <b>webAgent </b>component is placed in the right column of the page.<br><img src="../Storage/apizee-for-salesforce-publication-admin/configure-your-salesforce-environment/configure-your-salesforce-environment-2025-04-28.png" alt="" style="width: 100%; height: auto; max-width: 788px;" loading="lazy"><br></li> <li>Adjust the <b>height </b>and <b>width </b>of the component to fit the layout. </li> <li><i>(op</i><i>tional) If an error is displayed in the properties panel of the webAgent component, simply clear the <b>Object Name</b> field from any value and leave it blank.</i><br></li>
<li>Click <b>Save</b>. </li>
</ol>
<br><br>| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | The Apizee component is now visible in the Contact or Case detail page. |<br>| :--- | :--- |<br><br>
<br>*Repeat the operation for both Case and Contact Layouts.* |
| --- | --- |
| Assign a layout for Contact Object and Case Object (optional) | Assign a layout for Contact Object and Case Object (optional)
<br><br>| ![Information](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/info.png) | In this part, you will set up the default layout from Apizee instead of existing layouts.<br> <br>If you want to use your existing layouts, skip this step. |<br>| :--- | :--- |<br><br><ol style="text-align: left;"> <li>Connect to the target environment as a <b>System Administrator</b>. </li> <li>Open the <b>Setup</b> console. </li> <li>Navigate to <b>User Interface</b> &gt; <b>Lightning App Builder.</b> </li> <li> Click <b>View </b>for <b>Apizee Case Record Page</b> or <b>Apizee Contact Record Page.</b> <div> <img src="../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0015.png" alt="A screenshot of a computer  Description automatically generated" style="max-width: 601px; height: auto; width: 100%;" loading="lazy"> </div> <br> </li> <li> Click <b>Activation…</b> <br> <div> <img src="../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0016.png" alt="Une image contenant capture d’écran, texte, Rectangle, Police  Description générée automatiquement" style="max-width: 192px; height: auto; width: 100%;" loading="lazy"> </div> <br> </li> <li> Click <b>Assign as Org Default</b> to set the layout for all profiles or select the App, record type and profile for which you want the layout to be available. <br> <div> <img src="../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0017.png" alt="Une image contenant texte, capture d’écran, logiciel, Police  Description générée automatiquement" style="max-width: 510px; height: auto; width: 100%;" loading="lazy"> </div> </li> <li>Click <b>Desktop.</b> </li> <li> Click <b>Next. </b> </li> <li>Click <b>Save</b>. </li>
</ol>
<br><br>| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | The layout is now available to users for the Contact or Case detail page. |<br>| :--- | :--- |<br><br>
<br>*Repeat the operation for both Apizee Contact Layout and Apizee Case Layout.* |

## Add the Apizee component on Object Layout 

If you want to add component on an existing Layout page instead of using the default layout (see above).

1. Open **** a **Case** or **Contact** record detail.
2. Click **Settings** menu (circle in red below). ![Une image contenant texte, capture d’écran, logiciel, Icône d’ordinateur  Description générée automatiquement](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0020.png)
3. Click **Edit Page.** ![Une image contenant texte, capture d’écran, Police, nombre  Description générée automatiquement](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0021.png)
4. In the next window, scroll down the **Components list** in the left panel until you see the **webAgent** component. ![Une image contenant texte, capture d’écran, logiciel, Icône d’ordinateur  Description générée automatiquement](../Storage/apizee-for-salesforce-publication-admin/Imported/topic/img0022.png)
5. Drag the **webAgent** and drop it on one of the sections in the page layout. 
In the following example, the **webAgent** component is placed in the right column of the page.
![](../Storage/apizee-for-salesforce-publication-admin/configure-your-salesforce-environment/configure-your-salesforce-environment-2025-04-28.png)
6. Adjust the **height** and **width** of the component to fit the layout.
7. *(op* *tional) If an error is displayed in the properties panel of the webAgent component, simply clear the **Object Name** field from any value and leave it blank.*
8. Click **Save**.

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | The Apizee component is now visible in the Contact or Case detail page. |
| :--- | :--- |

Repeat the operation for both Case and Contact Layouts.

## Apizee Connector for Salesforce Setup 

1. Connect to your environment with a user account which have the **Apizee User** permission set assigned.
2. Open **** the **App Launcher** (Lightning) or **App selector** (Classic)
3. Click **Apizee**
4. Click the **Apizee Configuration** tab 
 ![](../Storage/apizee-for-salesforce-publication-admin/configure-your-salesforce-environment/configure-your-salesforce-environment-2025-11-14.png)
5. Fill in the **Identification Key** field with your tenant's identification key.

| ![Information](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/info.png) | Apizee Identification Key is provided by Apizee representatives or can be found on the [Apizee Embed portal](https://portal.apizee.com/). |
| :--- | :--- |

The default information for the fields **Log Level** and **Advanced Option** can be kept unless instructed otherwise.

| ![](../Storage/apizee-for-salesforce-publication-admin/project-content-reuse/ok.png) | The Apizee service is now configured to work in your Salesforce environement. |
| :--- | :--- |