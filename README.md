# Tableau Viz LWC Samples

This repository contains samples for how you can add the Tableau Viz Lightning Web Component (LWC) within the body of your component. Composition enables you to build on top of the Tableau Viz LWC to make it fits your own needs.

## Requirement:

[You need to install the Tableau Viz LWC from GitHub](https://github.com/tableau/tableau-viz-lwc)

## Samples:

- Localized Dashboards
    In this sample, we are setting the public vizUrl property depending on the end user's language set up on the org. We have localized the Superdashboard in Spanish, and French, and we published it on Tableau Public. The Component is going to display the French or Spanish dashboard if the Salesforce user has one these languages set as their default language in Salesforce. If the user has a different language, the English version of the dashboard is going to be shown.
