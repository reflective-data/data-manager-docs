---
layout: page
title: "Building Widget Rules"
category: dashboard
date: 2019-08-26 08:55:36
order: 1
---

There are two options for writing widget rules.

1. JSON
2. Query Explorer

## Option 1 - JSON

Example set of widget rules:

```
{
    "dimensions": "ga:deviceCategory,ga:country",
    "metrics": "ga:sessions",
    "sort": "-ga:sessions",
    "filters": "ga:deviceCategory==mobile",
    "segment": "sessions::condition::ga:country==Estonia",
    "maxResults": "10",
    "startDate": "30daysAgo",
    "endDate": "today"
}
```

### List of parameters

| Parameter                                                                                              | Required | Notes                                                                                                                                                                                         |
|--------------------------------------------------------------------------------------------------------|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [dimensions](https://developers.google.com/analytics/devguides/reporting/core/v3/reference#dimensions) | No       | A list of comma-separated dimensions for your Analytics data, such as ga:browser,ga:city.                                                                                                     |
| [metrics](https://developers.google.com/analytics/devguides/reporting/core/v3/reference#metrics)       | Yes      | A list of comma-separated metrics, such as ga:sessions,ga:bounces.                                                                                                                            |
| [sort](https://developers.google.com/analytics/devguides/reporting/core/v3/reference#sort)             | No       | A list of comma-separated dimensions and metrics indicating the sorting order and sorting direction for the returned data.                                                                    |
| [filters](https://developers.google.com/analytics/devguides/reporting/core/v3/reference#filters)       | No       | Dimension or metric filters that restrict the data returned for your request.                                                                                                                 |
| [segment](https://developers.google.com/analytics/devguides/reporting/core/v3/reference#segment)       | No       | Segments the data returned for your request.                                                                                                                                                  |
| [maxResults](https://developers.google.com/analytics/devguides/reporting/core/v3/reference#maxResults) | No       | The maximum number of rows to include in the response.                                                                                                                                        |
| [startDate](https://developers.google.com/analytics/devguides/reporting/core/v3/reference#startDate)   | Yes      | Start date for fetching Analytics data. Requests can specify a start date formatted as YYYY-MM-DD, or as a relative date (e.g., today, yesterday, or NdaysAgo where N is a positive integer). |
| [endDate](https://developers.google.com/analytics/devguides/reporting/core/v3/reference#endDate)       | Yes      | End date for fetching Analytics data. Request can specify an end date formatted as YYYY-MM-DD, or as a relative date (e.g., today, yesterday, or NdaysAgo where N is a positive integer).     |

Non-required parameters can be left empty or you can remove these lines alltogether. See two examples below, they are both valid and produce the same results.

```
{
    "dimensions": "",
    "metrics": "ga:sessions",
    "sort": "",
    "filters": "",
    "segment": "",
    "maxResults": "",
    "startDate": "30daysAgo",
    "endDate": "today"
}
```

```
{
    "metrics": "ga:sessions",
    "startDate": "30daysAgo",
    "endDate": "today"
}
```

## Option 2 - Query Explorer

This option leverages the [Query Explorer](https://ga-dev-tools.appspot.com/query-explorer/) provided by Google.

### Step 1 - Choose the parameters for your query

![img 1](https://i.imgur.com/6y1qbFi.png)

### Step 2 - Test your query by clicking "Run Query"

![img 2](https://i.imgur.com/5hnwjk5.png)

### Step 3 - Paste the "Direct link to this Report" value in the Widget Rules section

![img 3](https://i.imgur.com/uZJqHZI.png)

![img 4](https://i.imgur.com/K4borYf.png)
