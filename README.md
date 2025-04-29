# Creating and Uploading Satellite Manifest

## Introducing Manifest

A manifest is a set of encrypted files containing information about your subscriptions.

You can use a manifest to import your subscriptions into Red Hat Satellite. After the manifest is imported, you can use it to manage RHEL systems and synchronize content.

> [!NOTE]
> Users on a connected network create and manage their subscription manifests on the [Red Hat Hybrid Cloud Console](https://console.redhat.com), however, users on a disconnected network must use the [Red Hat Customer Portal](https://access.redhat.com).

An authorized Satellite user on a connected network can create, export, delete, and modify manifests from [Red Hat Hybrid Cloud Console](https://console.redhat.com).

### Prerequisites to create a Manifest from Red Hat Hybrid Cloud Console

- You are logged in to the [Red Hat Hybrid Cloud Console](https://console.redhat.com).

- You are connected to a Red Hat Satellite Server.

- You have Red Hat Satellite 6 or later.

- You have the Subscriptions administrator role in the role-based access control (RBAC) system for the [Red Hat Hybrid Cloud Console](https://console.redhat.com).

> [!NOTE]
> - If you do not have an active Satellite subscription and you have at least one existing subscription manifest for your account, then you can view and export your existing manifests, but the Create new manifest button is inactive until you reactivate your Satellite subscription.
> - If you do not have an active Satellite subscription and you have no existing subscription manifests for your account, then you can click the Contact button to receive help from Red Hat.

## Creating a Manifest using Red Hat Customer Portal 

> [!WARNING]
> Only a user with Org Admin (or organization administrator) role can create and manage the subscription and export the manifest.

> [!NOTE]
> The organization administrator is a role, so any number of users in one account can have it.

Login to the [Red Hat Customer Portal](https://access.redhat.com) with an account that has Org Admin right and Click on **Subscriptions** on the top left corner

![portal](/images/1-portal.png)

Click **Subscription Allocations** 

![allocation](/images/2-allocation.png)

Click **New Subscription Allocation** button

![new-subscription](/images/3-new_subscription.png)

Give the manifest a **name** and choose the **type** (version of Satellite) that will be used within the manifest, then click on **Create** button

![manifest_name](/images/4-manifest_name.png)

You will be able to see the below output once the manifest is successfully created

![success](/images/5-success.png)

Click on **Subscriptions** to add some subscriptions to your manifest and then click on **Add Subscriptions** button to see the available subscriptions that can be added to your manifest.

![add](/images/6-add.png)

Select the number of **Entitlements** for the Red Hat Product that you want to add to your Manifest. Scroll down to the bottom of the page and click **Submit** button.

> [!NOTE]
> You can use filter to search or manually browse the required subscriptions.

![available_1](/images/7-available_1.png)

![available_2](/images/8-available_2.png)

You will be able to see the success message once all the Product Entitlements are added successfully to your manifest. You can now click **Export Manifest** button to download the Manifest

![final](/images/9-final.png)

![export](/images/10-export.png)

## Importing the Manifest in Red Hat Satellite

Open a browser, enter the Red Hat Satellite Server URL - https://satellite.example.com

Enter Credentials and click Log In button

- Username: admin
- Password: redhat

![dashboard](/images/11-dashboard.png)

Click on the **Content > Subscriptions > Import a Manifest**

![import](/images/12-import.png)

Click on **browse** and select the downloaded Manifest from the path to start importing the Manifest

![browse](/images/13-browse.png)

![selecting](/images/14-selecting.png)

![importing](/images/15-importing.png)

You will see the subscriptions once your manifest is imported

![final_subscription](/images/16-final_subscription.png)

## References

[Creating and managing manifests for a connected Satellite Server](https://docs.redhat.com/en/documentation/subscription_central/1-latest/html-single/creating_and_managing_manifests_for_a_connected_satellite_server/index#proc-creating-manifest-satellite-connected)

