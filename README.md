# Creating and Uploading Satellite Manifest

## Introducing Manifest

A manifest is a set of encrypted files containing information about your subscriptions.

You can use a manifest to import your subscriptions into Red Hat Satellite. After the manifest is imported, you can use it to manage RHEL systems and synchronize content.

> [!NOTE]
> Users on a connected network create and manage their subscription manifests on the [Red Hat Hybrid Cloud Console](https://console.redhat.com), however, users on a disconnected network must use the [Red Hat Customer Portal](https://access.redhat.com).

An authorized Satellite user on a connected network can create, export, delete, and modify manifests from Red Hat Hybrid Cloud Console.

### Prerequisites to create a Manifest from Red Hat Hybrid Cloud Console

- You are logged in to the Red Hat Hybrid Cloud Console.

- You are connected to a Red Hat Satellite Server.

- You have Red Hat Satellite 6 or later.

- You have the Subscriptions administrator role in the role-based access control (RBAC) system for the Red Hat Hybrid Cloud Console.

> [!NOTE]
> - If you do not have an active Satellite subscription and you have at least one existing subscription manifest for your account, then you can view and export your existing manifests, but the Create new manifest button is inactive until you reactivate your Satellite subscription.
> - If you do not have an active Satellite subscription and you have no existing subscription manifests for your account, then you can click the Contact button to receive help from Red Hat.

> [!NOTE]
> I will be demonstrating creating a manifest using Red Hat Customer Portal.

## Creating a Manifest 

Login to the [Hybrid Cloud Console](https://console.redhat.com)

Click the drop down button - Red Hat Hybrid Cloud Console on the top-left corner

Click Subscriptions and Spend > Manifests

Subscriptions and Spend > Manifests.

- From the Manifests page, click Create new manifest.

- In the Name field, enter a unique name for the manifest.

- From the Type list, select the application type and version number that corresponds to your Red Hat Satellite Server.

- Click Create.
