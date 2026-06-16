This procedure explains how to collect the information required from Microsoft Entra ID to configure a SAML federation with Apizee Embed as an external service provider.
 
The procedure is written from the point of view of the Microsoft Entra ID tenant administrator and aims at collecting key information to be shared with Apizee to set up a Single-Sign on flow.

{% hint style="info" %}
*You must have administrator access to the Microsoft Entra ID tenant.*
  - You must be able to create an **Enterprise application**. - You must have permission to configure **Single Sign-On (SAML)**. 
{% endhint %}

## Overview of required information
 
During the procedure, you will collect the following information from Microsoft Entra ID:
 
* The **SAML IdP metadata URL** of the application.
* The **Identity Provider issuer identifier**.
* The **SAML login endpoint**.
* The configured **user identifier attribute**.

After you collect this information, send it to the integration partner.
 
## Create an enterprise application

1. Open the **Microsoft Entra admin center**.
2. In the left navigation panel, click **Enterprise applications**.
![](../.gitbook/assets/enterprise_applications_entraid.png)
3. Click **New application**.
![](../.gitbook/assets/create_appplication├зentraid.png)
4. Click **Create your own application**.
5. Enter a name for the application.
6. Select **Integrate any other application you don't find in the gallery (Non-gallery)**.
7. Click **Create**.
![](../.gitbook/assets/application_created_entraid.png)

{% hint style="success" %}
*The enterprise application is created.*
 
You are redirected to the configuration page of the new application.
{% endhint %}

## Retrieve key information

1. In the application page, locate the **Manage** section.
2. Click **Single sign-on**.
3. Select **SAML** as the single sign-on method.
4. In the **SAML Certificates** section, locate the field **App Federation Metadata Url**.
5. Copy the complete URL displayed in this field.
![](../.gitbook/assets/retrieve_SAML_entraid.png)
6. Save this value in your integration documentation.

{% hint style="success" %}
*You have the SAML IdP metadata URL.*
 
This URL provides the federation metadata of your Microsoft Entra ID tenant for this application.
{% endhint %}

## Verify the user identifier attribute

1. In the SAML configuration page, locate the section **Attributes & Claims**.
2. Click **Edit**.
3. Select the claim **Unique User Identifier (Name ID)**.
4. Check the configured **Source attribute**.
5. If necessary, change the source attribute to the email attribute used by your organization.
6. Click **Save**.

{% hint style="success" %}
*The user identifier attribute is configured.*
{% endhint %}

## Information to share with Apizee to set up SAML-based SSO
 
When you complete the procedure, send the following information to the integration partner:

* SAML IdP metadata URL
* Login URL
* Microsoft Entra Identifier
* SAML signing certificate (Base64)
* User identifier attribute used for NameID

{% hint style="info" %}
*These values do not expose user credentials.*
 
The metadata and certificates only describe the identity provider configuration required to establish the SAML federation.
{% endhint %}

