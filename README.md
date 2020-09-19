# Tableau Viz Lightning Web Component Samples

This repository contains sample code that shows how you can add the Tableau Viz Lightning web component (LWC) within the body of another Lightning web component. This feature of Lightning Web Components is known as composition. Composition enables you to build on top of the Tableau Viz Lightning web component to customize it and make it fit your own needs. One advantage of using composition to build your component is that you can benefit from the improvements made to the Tableau Viz Lightning web component without having to change your code.

To learn more about composition and how you can go about composing components, check out [Composition](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.create_components_compose_intro) in the Lightning Web Component Dev Guide.

## Requirements

-   [Install git](https://git-scm.com/downloads), if you haven't already done so.

-   In your Salesforce org, [Install the Tableau Viz LWC from GitHub](https://github.com/tableau/tableau-viz-lwc) or from the [AppExchange](https://appexchange.salesforce.com/appxListingDetail?listingId=a0N4V00000GF1cSUAT).

-   [Set Up Your Salesforce DX Environment](https://trailhead.salesforce.com/en/content/learn/projects/quick-start-lightning-web-components/set-up-salesforce-dx)

-   [Set Up Visual Studio Code](https://trailhead.salesforce.com/content/learn/projects/quick-start-lightning-web-components/set-up-visual-studio-code)

## Samples

-   [Localized Dashboards](https://github.com/tableau/tableau-viz-lwc-samples/tree/dev/force-app/main/default/lwc/tableauvizlwcdemo)

    In this sample, we set the public `vizUrl` property depending on the language the user has set up on the org. For the sample, we localized the Superstore dashboard in Spanish and French, and published it on Tableau Public. The sample component displays the French or Spanish dashboard if the Salesforce user has one these languages set as their default language in Salesforce. If the user has English or another language set, the English version of the dashboard is shown.

## Install the sample

The Localized Dashboards sample requires that you first install the Tableau Viz Lighting web component in your org. You can install the Tableau Viz Lighting web component in one of two ways:

-   From the AppExchange

-   By cloning and installing the [tableau-viz-lwc](https://github.com/tableau/tableau-viz-lwc) project from GitHub

How you install the Tableau Viz Lightning web component determines how you need to install the sample. If you installed the component from the AppExchange, you need to make a modification to one of the configuration files for the sample. The following instructions describe how to install the sample for both scenarios. These instructions assume that you are using a [Developer Edition Org](https://developer.salesforce.com/signup) or a sandbox.

1. Open a Command or Terminal window and authorize the org where you installed the the Tableau Viz component from AppExchange. Provide it with an alias (**mydevorg** in the following command):

    ```
      sfdx force:auth:web:login -s -a mydevorg
    ```

1. Clone this repository (**tableau-viz-lwc-samples**) :

    ```
    git clone https://github.com/tableau/tableau-viz-lwc-samples

    ```

1. Navigate to the directory of the repository you just cloned.

    ```
    cd tableau-viz-lwc-samples

    ```

---

**Note:** If you installed the Tableau Viz Lightning component from AppExchange, you need to specify the `namespace` the sample uses before you can deploy the sample to your org. In the sample project, the `namespace` is not specified. By default, packages use the default namespace `c`, which will not work if you have installed the Tableau Viz Lightning web component from the AppExchange. You can skip this step if you didn't install the component from the AppExchange.

-   Edit the `sfdx-project.json` file in your `tableau-viz-lwc` folder and specify `"tab"` as the namespace.

    ```json
    {
        "packageDirectories": [
            {
                "path": "force-app",
                "default": true
            }
        ],
        "namespace": "tab",
        "sfdcLoginUrl": "https://login.salesforce.com",
        "sourceApiVersion": "48.0"
    }
    ```

---

### Deploy the sample

1. Run this command in a terminal to deploy the component.

    ```
    sfdx force:source:deploy -p force-app
    ```

    If see an error message that asks you to specify a username or an error message that says that the `tableauViz` module is not found, use the following command and replace `username` with the login name you use for `mydevorg` or for the username associated with the org where you deployed the `tableau-viz-lwc` component from GitHub.

    ```
    sfdx force:source:deploy -p force-app -u username
    ```

1. If your org isn't already open, open it now:

    ```
    sfdx force:org:open -u mydevorg
    ```

    This opens Salesforce and takes you to your Developer Edition Org. When you edit a Lightning page, the **Tableau Visualization** and **Tableau Viz Sample** should both appear and be available under Components.

    Note that you might need to specify a different `-u username` for the org where you installed the `tableau-viz-lwc` component. The deployment will fail if the Tableau Viz Lightning web component and the is not installed and the `tableauViz` is module is not available. You can check your setup by using the following command.

    ```
    sfdx force:org:list

    ```

## Try out the sample

To see the Tableau sample in action try the following steps.

1. Add the `Tableau Viz Sample` to a Lightning record page. The sample view changes language based on the language setting a user has enabled in Salesforce.

1. To change to the language settings in Salesforce org, click the User icon in the top-right corner of the browser.

1. Click **Settings**.

1. Under My Personal Information, click **Language & Time Zone**.

1. Choose French, Spanish, or English from the **Language** drop-down menu and save your settings.

    If you are not familiar with the language you are changing to, be sure to note the location of the menu items you've selected, so that you can revert to the language you started from.

1. Return to the page where you added the `Tableau Viz Sample` and observe the change in the language displayed in the view.
