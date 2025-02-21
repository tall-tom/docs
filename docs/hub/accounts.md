# Installation and Account Setup

To create an account, you need first to install the Hub CLI. The CLI is where you are going to do all account management, create orgs, create API keys, etc. The first step is to download and install the application. 

## Install the Command-line Interface

### Download

Download the Hub CLI binary for your platform from the [latest releases](https://github.com/textileio/textile/releases/latest).

!!!info
  
    You'll see two binaries available for download on the Textile releases page, `hub`, and `buck`. Ignore the `buck` binary for now. `buck` is used to interact with buckets in a stand-alone manner, independent of Textile Hub. `hub` provides all the functionality you'll need to interact with the Textile Hub and Buckets together.

### Install

![Open the contents of the downloaded archive and run the `install` script. This should install the `hub` tool on your computer. You can verify with `hub --help`.](../images/install/install.png)

#### Mac Installation

On MacOS you will need to confirm that it is okay to run the `hub` binary before it runs successfully. You will see this warning:

![Select 'Cancel'](../images/install/install_warn.png)

![Go to 'System Settings' => 'General' where you will be able to click, 'Allow Anyway'](../images/install/install_allow.png)

![Run `hub --help` again and this time select, 'Open` when prompted.](../images/install/install_confirm.png)

You will now be able to continue using the CLI without issue. When you update the binary, you may need to repeat the above steps. We will add developer signing to our MacOS binaries soon.

![Successfully running `hub --help` to print out the command docs.](../images/hub-cli/hub_help.png)

## Account setup

The next step is to initialize an account. The Hub CLI use magic-link signin, so it only requires you to enter and verify a valid email.

### Initialize

![](../images/hub-cli/hub_init.png)

```sh
hub init
```

You have now created an account on the Textile Hub! You can now run all the available commands, such as `hub --help`, `hub whoami`, `hub buckets`, `hub keys ls`, `hub logout`, and `hub login`.

### Login

Now that your account exists, the next time you use the CLI on a new computer, or after logging out, you simply need to `login`.

```sh
hub login
```

## Organizations

`Orgs` allow multiple developers to work together using shared resources. Members of an organization can collaboratively manage, create, or remove [API keys](../hub/apis.md#app-keys), and more.

You can create an `org` easily.

![](../images/hub-cli/hub_org_create.png)

```sh
hub org create
```

Next, you can begin inviting collaborators by email addresses.

![](../images/hub-cli/hub_org_invite.png)

```sh
hub org invite
```

You can now share and collaborate with all `org` members. For example, when creating new buckets, you can create them in the `org` and immediately be available to your collaborators. Additionally, you can create and share API key admin.

**Org bucket init**

```sh
HUB_ORG=<org name> hub buck init
```

**Org keys create**

```sh
HUB_ORG=<org name> hub keys create
```

!!!info
    You can [create](../hub/cli/hub_orgs_create.md), [invite](../hub/cli/hub_orgs_invite.md), and [leave](../hub/cli/hub_orgs_leave.md) organizations easily. Read more about all Org methods on the [CLI docs](../hub/cli/hub_orgs.md).

To learn more about sharing Buckets with an organization, read the intro on [Organization Buckets](../buckets/index.md#organization-buckets).

## Enterprise users

If you are interested in enterprise support from Textile, please email us at [support@textile.io](mailto:support@textile.io).

## Account deletion

If you delete your account or organization, data replicated on IPFS through any API will **also be removed**. So if you remove your account, we highly encourage you to replicate the data on an external IPFS node, provide tools for your users to export or replicate their account data, or host external Thread Services to migrate your user Thread replication to.
