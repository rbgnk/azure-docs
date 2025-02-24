---
title: Getting started with Azure metrics explorer
description: Learn how to create your first metric chart with Azure metrics explorer.
author: vgorbenko
services: azure-monitor
ms.topic: conceptual
ms.date: 02/21/2022
ms.author: vitalyg
ms.reviewer: vitalyg
---

# Getting started with Azure Metrics Explorer

## Where do I start
Azure Monitor metrics explorer is a component of the Microsoft Azure portal that allows plotting charts, visually correlating trends, and investigating spikes and dips in metrics' values. Use the metrics explorer to investigate the health and utilization of your resources. Start in the following order:

1. [Pick a resource and a metric](#create-your-first-metric-chart) and you see a basic chart. Then [select a time range](#select-a-time-range) that is relevant for your investigation.

1. Try [applying dimension filters and splitting](#apply-dimension-filters-and-splitting). The filters and splitting allow you to analyze which segments of the metric contribute to the overall metric value and identify possible outliers.

1. Use [advanced settings](#advanced-chart-settings) to customize the chart before pinning to dashboards. [Configure alerts](../alerts/alerts-metric-overview.md) to receive notifications when the metric value exceeds or drops below a threshold.

## Create your first metric chart

To create a metric chart, from your resource, resource group, subscription, or Azure Monitor view, open the **Metrics** tab and follow these steps:

1. Select the "Select a scope" button to open the resource scope picker. This allows you to select the resource(s) you want to see metrics for. The resource should already be populated if you opened metrics explorer from the resource's menu. To learn how to view metrics across multiple resources, [read this article](./metrics-dynamic-scope.md).
    > ![Select a resource](./media/metrics-getting-started/scope-picker.png)

1. For some resources, you must pick a namespace. The namespace is just a way to organize metrics so that you can easily find them. For example, storage accounts have separate namespaces for storing Files, Tables, Blobs, and Queues metrics. Many resource types only have one namespace.

1. Select a metric from a list of available metrics.

    > ![Select a metric](./media/metrics-getting-started/metrics-dropdown.png)

1. Optionally, you can [change the metric aggregation](../essentials/metrics-charts.md#aggregation). For example, you might want your chart to show minimum, maximum, or average values of the metric.

> [!TIP]
> Use the **Add metric** button and repeat these steps if you want to see multiple metrics plotted in the same chart. For multiple charts in one view, select the **Add chart** button on top.

## Select a time range

> [!WARNING]
> [Most metrics in Azure are stored for 93 days](../essentials/data-platform-metrics.md#retention-of-metrics). However, you can query no more than 30 days worth of data on any single chart. You can [pan](metrics-charts.md#pan) the chart to view the full retention. The 30 day limitation doesn't apply to [log-based metrics](../app/pre-aggregated-metrics-log-metrics.md#log-based-metrics).

By default, the chart shows the most recent 24 hours of metrics data. Use the **time picker** panel to change the time range, zoom in, or zoom out on your chart. 

![Change time range panel](./media/metrics-getting-started/time.png)

> [!TIP]
> Use the **time brush** to investigate an interesting area of the chart (spike or a dip). Put the mouse pointer at the beginning of the area, click and hold the left mouse button, drag to the other side of area and then release the button. The chart will zoom in on that time range. 

## Apply dimension filters and splitting

[Filtering](../essentials/metrics-charts.md#filters) and [splitting](../essentials/metrics-charts.md#apply-splitting) are powerful diagnostic tools for the metrics that have dimensions. These features show how various metric segments ("dimension values") impact the overall value of the metric, and allow you to identify possible outliers.

- **Filtering** lets you choose which dimension values are included in the chart. For example, you might want to show successful requests when charting the *server response time* metric. You would need to apply the filter on the *success of request* dimension. 

- **Splitting** controls whether the chart displays separate lines for each value of a dimension, or aggregates the values into a single line. For example, you can see one line for an average response time across all server instances, or see separate lines for each server. You would need to apply splitting on the *server instance* dimension to see separate lines.

See [examples of the charts](../essentials/metric-chart-samples.md) that have filtering and splitting applied. The article shows the steps were used to configure the charts.

## Share your metric chart
There are three ways to share your metric chart. See the instructions below on how to share information from your metrics charts using Excel, a link and a workbook.
 
### Download to Excel
Select "Share" and "Download to Excel". Your download should start immediately.

:::image type="content" source="media/metrics-getting-started/share-excel.png" alt-text="screenshot how to share metric chart using excel":::

### Share a link
Select "Share" and "Copy link". You should get a notification that the link was copied successfully.

:::image type="content" source="media/metrics-getting-started/share-link.png" alt-text="screenshot how to share metric chart using a link":::

### Send to workbook
Select "Share" and "Send to Workbook". The **Send to Workbook** window opens for you to send the metric chart to a new or existing workbook.

:::image type="content" source="media/metrics-getting-started/share-workbook.png" alt-text="screenshot how to share metric chart to a workbook":::


## Advanced chart settings

You can customize chart style, title, and modify advanced chart settings. When done with customization, pin it to a dashboard  or save to a workbook to save your work. You can also configure metrics alerts. Follow [product documentation](../essentials/metrics-charts.md) to learn about these and other advanced features of Azure Monitor metrics explorer.

## Next steps

* [Learn about advanced features of Metrics Explorer](../essentials/metrics-charts.md)
* [Viewing multiple resources in Metrics Explorer](./metrics-dynamic-scope.md)
* [Troubleshooting Metrics Explorer](metrics-troubleshoot.md)
* [See a list of available metrics for Azure services](./metrics-supported.md)
* [See examples of configured charts](../essentials/metric-chart-samples.md)
