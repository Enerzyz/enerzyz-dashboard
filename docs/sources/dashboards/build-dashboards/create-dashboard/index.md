---
aliases:
  - add-organize-panels/
keywords:
  - panel
  - dashboard
  - create
labels:
  products:
    - cloud
    - enterprise
    - oss
menuTitle: Create a dashboard
title: Create a dashboard
weight: 1
---

## Create a dashboard

Dashboards and panels allow you to show your data in visual form. Each panel needs at least one query to display a visualization.

**Before you begin:**

- Ensure that you have the proper permissions. For more information about permissions, refer to [About users and permissions]({{< relref "../../../administration/roles-and-permissions/" >}}).
- Identify the dashboard to which you want to add the panel.
- Understand the query language of the target data source.
- Ensure that data source for which you are writing a query has been added. For more information about adding a data source, refer to [Add a data source]({{< relref "../../../administration/data-source-management#add-a-data-source" >}}) if you need instructions.

**To create a dashboard**:

1. Click **Dashboards** in the left-side menu.
1. Click **New** and select **New Dashboard**.
1. On the empty dashboard, click **+ Add visualization**.

   ![Empty dashboard state](/media/docs/grafana/dashboards/empty-dashboard-9.5.png)

1. In the modal that opens, do one of the following:

   - Select one of your existing data sources.
   - Select one of the Grafana's [built-in special data sources]({{< relref "../../../datasources/#special-data-sources" >}}).
   - Click **Configure a new data source** to set up a new one (Admins only).

   {{< figure class="float-right"  src="/media/docs/grafana/dashboards/screenshot-data-source-selector-10.0.png" max-width="800px" alt="Select data source modal" >}}

   The **Edit panel** view opens with your data source selected.
   You can change the panel data source later using the dropdown in the **Query** tab of the panel editor if needed.

   For more information about data sources, refer to [Data sources]({{< relref "../../../datasources/" >}}) for specific guidelines.

1. Write or construct a query in the query language of your data source.

1. Click the Refresh dashboard icon to query the data source.

   ![Refresh dashboard icon](/media/docs/grafana/dashboards/screenshot-refresh-dashboard-9.5.png)

1. In the visualization list, select a visualization type.

   ![Visualization selector](/media/docs/grafana/dashboards/screenshot-select-visualization-9-5.png)

   Grafana displays a preview of your query results with the visualization applied.

   For more information about individual visualizations, refer to [Visualizations options]({{< relref "../../../panels-visualizations/visualizations/" >}}).

1. Refer to the following documentation for ways you can adjust panel settings.

   While not required, most visualizations need some adjustment before they properly display the information that you need.

   - [Configure value mappings]({{< relref "../../../panels-visualizations/configure-value-mappings" >}})
   - [Visualization-specific options]({{< relref "../../../panels-visualizations/visualizations/" >}})
   - [Override field values]({{< relref "../../../panels-visualizations/configure-overrides/" >}})
   - [Configure thresholds]({{< relref "../../../panels-visualizations/configure-thresholds/" >}})
   - [Configure standard options]({{< relref "../../../panels-visualizations/configure-standard-options/" >}})

1. When you've finished editing your panel, click **Save** to save the dashboard.

   Alternatively, click **Apply** if you want to see your changes applied to the dashboard first. Then click the save icon in the dashboard header.

1. Enter a name for your dashboard and select a folder, if applicable.
1. Click **Save**.
1. To add more panels to the dashboard, click **Add** in the dashboard header and select **Visualization** in the dropdown.

   ![Add dropdown](/media/docs/grafana/dashboards/screenshot-add-dropdown-10.0.png)

   When you add additional panels to the dashboard, you're taken straight to the **Edit panel** view.

## Configure repeating rows

You can configure Grafana to dynamically add panels or rows to a dashboard based on the value of a variable. Variables dynamically change your queries across all rows in a dashboard. For more information about repeating panels, refer to [Configure repeating panels]({{< relref "../../../panels-visualizations/configure-panel-options/#configure-repeating-panels" >}}).

To see an example of repeating rows, refer to [Dashboard with repeating rows](https://play.grafana.org/d/000000153/repeat-rows). The example shows that you can also repeat rows if you have variables set with `Multi-value` or `Include all values` selected.

**Before you begin:**

- Ensure that the query includes a multi-value variable.

**To configure repeating rows:**

1. Click **Dashboards** in the left-side menu.
1. Navigate to the dashboard you want to work on.
1. At the top of the dashboard, click **Add** and select **Row** in the dropdown.

   If the dashboard is empty, you can click the **+ Add row** button in the middle of the dashboard.

1. Hover over the row title and click the cog icon.
1. In the **Row Options** dialog box, add a title and select the variable for which you want to add repeating rows.
1. Click **Update**.

To provide context to dashboard users, add the variable to the row title.

### Repeating rows and the Dashboard special data source

If a row includes panels using the special [Dashboard]({{< relref "../../../datasources/#special-data-sources" >}}) data source&mdash;the data source that uses a result set from another panel in the same dashboard&mdash;then corresponding panels in repeated rows will reference the panel in the original row, not the ones in the repeated rows.

For example, in a dashboard:

- `Row 1` includes `Panel 1A` and `Panel 1B`
- `Panel 1B` uses the results from `Panel 1A` by way of the `-- Dashboard --` data source
- Repeating row, `Row 2`, includes `Panel 2A` and `Panel 2B`
- `Panel 2B` references `Panel 1A`, not `Panel 2A`

## Move a panel

You can place a panel on a dashboard in any location.

1. Click **Dashboards** in the left-side menu.
1. Navigate to the dashboard you want to work on.
1. Click the panel title and drag the panel to the new location.

## Resize a panel

You can size a dashboard panel to suits your needs.

1. Click **Dashboards** in the left-side menu.
1. Navigate to the dashboard you want to work on.
1. To adjust the size of the panel, click and drag the lower-right corner of the panel.
