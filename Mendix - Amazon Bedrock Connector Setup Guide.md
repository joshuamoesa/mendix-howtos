# Mendix - Amazon Bedrock Connector Setup Guide

## Overview
This guide describes how to configure the **Amazon Bedrock Connector** locally using the **GenAI Showcase App** as the target application.

## Prerequisites
Before starting, ensure you have the following ready:
* AWS Account
* Mendix Studio Pro 10.24
* Mendix GenAI Showcase App

---

## 1. Get AWS Temporary Credentials
To get temporary AWS credentials, the GenAI Showcase App leverages the **AWS Authentication Connector**. For complete documentation, see the [Mendix AWS Authentication Documentation](https://docs.mendix.com/appstore/modules/aws/aws-authentication/#session).

Follow the steps outlined in the **AWS - IAM Roles Anywhere** guide to set up roles.

---

## 2. Setup for Local Testing in Mendix Studio Pro

### Step 2.1: Add Client Certificate
Using the client certificate generated in the *AWS - IAM Roles Anywhere* setup, follow these steps to add it to your local environment:

1. Open your project in **Mendix Studio Pro**.
2. Navigate to **Settings > Configurations** and double-click on the **Default** configuration.
3. Select the **Custom** tab.
4. Add the following setting variables:

| Name | Value |
| :--- | :--- |
| `ClientCertificatePasswords` | `<YOUR_CERTIFICATE_PASSWORD>` |
| `ClientCertificates` | `<FULL_PATH_TO_YOUR_CERTIFICATE>/client.p12` |

---

### Step 2.2: Add Constants Configuration
1. Open **Settings > Configurations** and edit the **Default** configuration.
2. Select the **Constants** tab.
3. Click **New** or **Edit** to define or override the following constants:

| Constant | Value |
| :--- | :--- |
| `AWSAuthentication.ClientCertificateID` | `1` |
| `AWSAuthentication.Duration` | `900` |
| `AWSAuthentication.ProfileARN` | `arn:aws:rolesanywhere:<AWS_REGION>:<AWS_ACCOUNT_ID>:profile/<PROFILE_UUID>` |
| `AWSAuthentication.RoleARN` | `arn:aws:iam::<AWS_ACCOUNT_ID>:role/<YOUR_IAM_ROLE_NAME>` |
| `AWSAuthentication.SessionName` | `<YOUR_SESSION_NAME>` |
| `AWSAuthentication.TrustAnchorARN` | `arn:aws:rolesanywhere:<AWS_REGION>:<AWS_ACCOUNT_ID>:trust-anchor/<TRUST_ANCHOR_UUID>` |
| `Encryption.EncryptionKey` | `<YOUR_ENCRYPTION_KEY>` |

#### Configuration UI Reference
Below is the Mendix Studio Pro configuration window for your constants reference:

![Mendix Constants Configuration](./images/mendix_constants_config.png)

---

## AWS Configuration Reference Details

### Trust Anchor Details
* **Name:** `<YOUR_TRUST_ANCHOR_NAME>`
* **Trust Anchor ID:** `<TRUST_ANCHOR_UUID>`
* **ARN:** `arn:aws:rolesanywhere:<AWS_REGION>:<AWS_ACCOUNT_ID>:trust-anchor/<TRUST_ANCHOR_UUID>`

![AWS Trust Anchor Details](./images/aws_trust_anchor.png)

### Profile Details
* **Profile ID:** `<PROFILE_UUID>`
* **ARN:** `arn:aws:rolesanywhere:<AWS_REGION>:<AWS_ACCOUNT_ID>:profile/<PROFILE_UUID>`

![AWS Profile Details](./images/aws_profile_details.png)

### Role Details
* **Role ARN:** `arn:aws:iam::<AWS_ACCOUNT_ID>:role/<YOUR_IAM_ROLE_NAME>`
* **Maximum Session Duration:** `1 hour`
