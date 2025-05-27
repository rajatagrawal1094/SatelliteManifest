# Creating and Uploading Satellite Manifest

[Red Hat Satellite Learning Series Main Menu](https://github.com/rajatagrawal1094/RedHatSatellite)

## Table of Contents
- [Introduction](#introduction)
- [What is Manifest?](#introducing-manifest)
- [Prerequisites for creating a Manifest from Red Hat Hybrid Cloud Console](#prerequisites-to-create-a-manifest-from-red-hat-hybrid-cloud-console)
- [Creating a Manifest using Red Hat Customer Portal](#creating-a-manifest-using-red-hat-customer-portal)
- [Importing the Manifest in Red Hat Satellite](#importing-the-manifest-in-red-hat-satellite)
- [Summary](#summary)

## Introduction

Red Hat Satellite uses a Subscription Manifest to manage and allocate product entitlements across your organization’s systems. This guide is intended for Red Hat Satellite administrators working in a connected network environment. By following this tutorial, you will learn how to create a Subscription Manifest using the Red Hat Customer Portal, and then upload it to your Satellite Server through the web UI and command-line interface. This process enables content synchronization and subscription management for your Red Hat Enterprise Linux infrastructure.


## Introducing Manifest

A Manifest is a set of encrypted files containing information about your subscriptions.

You can use a Manifest to import your subscriptions into Red Hat Satellite. After the Manifest is imported, you can use it to manage RHEL systems and synchronize content.

> [!NOTE]
> Users on a connected network create and manage their Subscription Manifests on the [Red Hat Hybrid Cloud Console](https://console.redhat.com), however, users on a disconnected network must use the [Red Hat Customer Portal](https://access.redhat.com).

An authorized Satellite user on a connected network can create, export, delete, and modify Manifests from [Red Hat Hybrid Cloud Console](https://console.redhat.com).

## Prerequisites for Creating a Manifest from Red Hat Hybrid Cloud Console

- You are logged in to the [Red Hat Hybrid Cloud Console](https://console.redhat.com).

- You are connected to a Red Hat Satellite Server.

- You have Red Hat Satellite 6 or later.

- You have the Subscriptions administrator role in the role-based access control (RBAC) system for the [Red Hat Hybrid Cloud Console](https://console.redhat.com).

> [!NOTE]
> - If you do not have an active Satellite subscription and you have at least one existing Subscription Manifest for your account, then you can view and export your existing Manifests, but the Create new Manifest button is inactive until you reactivate your Satellite subscription.
> - If you do not have an active Satellite subscription and you have no existing Subscription Manifests for your account, then you can click the Contact button to receive help from Red Hat.

## Creating a Manifest using Red Hat Customer Portal 

> [!WARNING]
> Only a user with Org Admin (or organization administrator) role can create and manage the subscription and export the Manifest.

> [!NOTE]
> The organization administrator is a role, so any number of users in one account can have it.

Log in to the [Red Hat Customer Portal](https://access.redhat.com) using an account that has Org Admin right and Click on **Subscriptions** on the top left corner

![portal](/images/1-portal.png)

Click **Subscription Allocations** 

![allocation](/images/2-allocation.png)

Click **New Subscription Allocation** button

![new-subscription](/images/3-new_subscription.png)

Give the Manifest a **name** and choose the **type** (version of Satellite) that will be used within the Manifest, then click on **Create** button

![manifest_name](/images/4-manifest_name.png)

You will see the following output once the Manifest is successfully created

![success](/images/5-success.png)

Click **Subscriptions** to view or add entitlements. Then click on **Add Subscriptions** button to see the available subscriptions that can be added to your Manifest.

![add](/images/6-add.png)

Select the number of **Entitlements** for the Red Hat Product that you want to add to your Manifest. Scroll down to the bottom of the page and click **Submit** button.

> [!NOTE]
> You can use filter to search or manually browse the required subscriptions.

![available_1](/images/7-available_1.png)

![available_2](/images/8-available_2.png)

You will be able to see the success message once all the Product Entitlements are added successfully to your Manifest. Click the **Export Manifest** button to download the Manifest

![final](/images/9-final.png)

![export](/images/10-export.png)

## Importing the Manifest in Red Hat Satellite

Open a browser, enter the Red Hat Satellite Server URL - https://satellite.example.com

Enter Credentials and click Log In button

- **Username**: admin
- **Password**: redhat

![dashboard](/images/11-dashboard.png)

Navigate to **Content > Subscriptions > Import a Manifest**

![import](/images/12-import.png)

Click on **Browse** and select the downloaded Manifest from the path to start importing the Manifest

![browse](/images/13-browse.png)

![selecting](/images/14-selecting.png)

![importing](/images/15-importing.png)

You can optionally run the below command to import the Manifest

> [!NOTE]
> This CLI method is useful for automating Manifest uploads in scripted or headless environments.

```console
[ragrawal@satellite ~]$ hammer subscription upload --file <path_to_file> --organization <organization_name>
```

![subscription_upload_cli](/images/16-subscription_upload_cli.png)

You will see the subscriptions once your Manifest is imported

![final_subscription](/images/17-final_subscription.png)

You can optionally run the below command to list the available subscriptions on the CLI

```console
[ragrawal@satellite ~]$ hammer subscription list --organization <organization_name>
```

## Summary

By completing these steps, you have learned how to create and upload a Satellite Subscription Manifest in a connected network environment. You:

- Logged into the Customer Portal to generate a Subscription Manifest.
- Added relevant product entitlements to the Manifest.
- Exported and downloaded the Manifest file.
- Uploaded the Manifest to Red Hat Satellite via the web interface and optionally via the CLI.

Your Red Hat Satellite Server is now ready to manage subscriptions and synchronize content based on the imported entitlements.

## References

[Creating and managing manifests for a connected Satellite Server](https://docs.redhat.com/en/documentation/subscription_central/1-latest/html-single/creating_and_managing_manifests_for_a_connected_satellite_server/index#proc-creating-manifest-satellite-connected)

