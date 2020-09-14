# Tableau Viz LWC Samples

This repository contains samples for how you can add the Tableau Viz Lightning Web Component (LWC) within the body of your component. Composition enables you to build on top of the Tableau Viz LWC to make it fits your own needs.

To learn more about composition, check out the Lightning Web Component Dev Guide [here](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.create_components_compose_intro)

## Requirement:

-   [You need to install the Tableau Viz LWC from GitHub](https://github.com/tableau/tableau-viz-lwc)
-   [Set Up Your Salesforce DX Environment](https://trailhead.salesforce.com/en/content/learn/projects/quick-start-lightning-web-components/set-up-salesforce-dx)
-   [Set Up Visual Studio Code](https://trailhead.salesforce.com/content/learn/projects/quick-start-lightning-web-components/set-up-visual-studio-code)

## Samples:

-   [Localized Dashboards](https://github.com/tableau/tableau-viz-lwc-samples/tree/dev/force-app/main/default/lwc/tableauvizlwcdemo)

    In this sample, we are setting the public vizUrl property depending on the end user's language set up on the org. We have localized the Superdashboard in Spanish, and French, and we published it on Tableau Public. The Component is going to display the French or Spanish dashboard if the Salesforce user has one these languages set as their default language in Salesforce. If the user has a different language, the English version of the dashboard is going to be shown.
