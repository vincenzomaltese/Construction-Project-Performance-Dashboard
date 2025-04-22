# Construction Project Performance Dashboard

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT) [![Powered by Power BI](https://img.shields.io/badge/Powered%20by-Power%20BI-yellow?style=for-the-badge&logo=powerbi)](https://powerbi.microsoft.com/)

## 📊 Project Overview

This repository contains a comprehensive Power BI dashboard designed for **Construction Project Management**. Leveraging data visualization best practices, this dashboard provides a holistic view of project performance, enabling stakeholders, project managers, and executives to monitor progress, track key performance indicators (KPIs), identify potential risks, and make informed, data-driven decisions.

The solution transforms raw project data into actionable insights, focusing on cost, budget, timelines, task completion, resource allocation, and profitability across the entire project portfolio.

---

## ✨ Key Features & Dashboard Sections

The Power BI report consists of two main interactive pages:

### 1. Overview Dashboard

This page provides a high-level executive summary of the entire project portfolio. Key components include:

*   **KPI Cards:** At-a-glance metrics for `Total Projects`, `Total Tasks`, `Total Cost`, `Total Budget`, and `Overall Profit`.
*   **Gauges:** Visual indicators for `Budget Utilization %` and overall `Task Completion %`.
*   **Trend Analysis:**
    *   `Cost & Budget by Month`: Line chart tracking spending against budget over time, crucial for identifying potential overruns or underspends.
    *   `Profit by Month`: Bar chart illustrating monthly profitability trends.
*   **Status & Categorization:**
    *   `Projects by Project Status`: Donut chart showing the distribution of projects by their current status (e.g., On Track, Behind, On Hold, Completed).
    *   `Tasks by Priority`: Bar chart breaking down tasks by priority level (High, Medium, Low).
    *   `Tasks by Progress Group`: Bar chart visualizing task distribution based on completion percentage brackets.
    *   `Tasks by Project Type`: Bar chart showing task volume across different project types (e.g., Renovation, Construction, Infrastructure).
*   **Performance & Location Insights:**
    *   `PM Performance Table`: Matrix detailing key metrics (Tasks, Overdue Tasks, Cost, Budget, Profit) for each Project Manager, including their picture for easy identification.
    *   `Tasks and Projects by Location`: Geographic map visualizing the distribution of projects and tasks across different states/regions.

![Overview Dashboard](https://github.com/vincenzomaltese/Construction-Project-Performance-Dashboard/blob/main/images/overview.jpg)

### 2. Project Timeline (Gantt Chart View)

This page offers a detailed, task-level view of project schedules using an interactive Gantt chart. Key features include:

*   **Hierarchical View:** Projects can be expanded to show individual tasks.
*   **Timeline Visualization:** Task durations are represented by bars plotted against a clear timeline axis (Months/Years).
*   **Status Indication:** Color-coded bars represent task status (`Completed`, `In Progress`, `Pending`), based on the legend.
*   **Resource Assignment:** Displays the name of the individual assigned to each task (e.g., Frank, Bob, Alice).
*   **Interactivity:** Includes a `Search` bar to find specific projects or tasks and a `Collapse All` button for easier navigation.

![Timeline Project](https://github.com/vincenzomaltese/Construction-Project-Performance-Dashboard/blob/main/images/project_timeline.jpg)

---

## 🏗️ Data Model

The dashboard is built upon a robust Star Schema data model, optimized for performance and analytical flexibility within Power BI:

*   **Fact Table:**
    *   `Project Management`: A central fact table containing transactional data at the task level, including identifiers for projects, tasks, managers, status, type, and key dates (e.g., `Start Date`, likely an implied `End Date` used for Gantt calculation).
*   **Dimension Tables:**
    *   `dimProjectManager`: Contains details about Project Managers (ID, Name, Picture).
    *   `dimProjectStatus`: Defines different project statuses (ID, Status Name).
    *   `dimProjectType`: Lists various project types (ID, Type Name).
    *   `dimTaskStatus`: Defines different task statuses (ID, Status Name). Used for Gantt chart coloring.
    *   `dimLocation`: Contains location details (ID, Location Name - e.g., State/Region).
    *   `dimPriority`: Defines task priority levels (ID, Priority Name).
    *   `Calendar`: A standard date dimension table supporting time intelligence calculations and filtering.
*   **Measures Table:**
    *   `All Measures`: A dedicated table housing all DAX (Data Analysis Expressions) calculations for KPIs, percentages, and other derived metrics presented in the visuals.

Relationships are primarily one-to-many, flowing from the dimension tables to the fact table, enabling efficient filtering and slicing of data across different attributes.

---

## 💡 Potential Insights & Business Value

This dashboard empowers users to:

*   Gain a **consolidated view** of portfolio health and performance.
*   **Proactively identify risks** related to budget overruns, schedule delays, and overdue tasks.
*   **Monitor resource allocation** and task assignments across different projects.
*   **Evaluate Project Manager performance** based on key financial and operational metrics.
*   **Analyze trends** in cost, budget, and profitability over time.
*   **Understand project distribution** by status, type, priority, and location.
*   **Improve communication** with stakeholders through clear, interactive visualizations.
*   **Facilitate data-driven decision-making** for project planning and execution.

---

## 🛠️ Technology Stack

*   **Data Visualization & Analysis:** Microsoft Power BI Desktop
*   **Data Modeling:** Power Query, DAX (for calculations and measures)

---

## 🚀 How to Use

1.  **Prerequisites:** Requires Microsoft Power BI Desktop installed.
2.  **Open:** Download the `.pbix` file from this repository.
3.  **Interact:** Open the file in Power BI Desktop.
    *   Navigate between the `Overview` and `Project Timeline` tabs.
    *   Utilize slicers and filters (implicitly, by clicking on visuals) to drill down into specific data points.
    *   Hover over visuals to see tooltips with detailed information.
    *   Expand/collapse hierarchies in the Gantt chart.
    *   Use the search functionality on the Timeline page.


---
