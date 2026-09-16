# Project Management Analytics Dashboard – Power BI

A Power BI dashboard built to analyse project progress, milestones, daily activities, modules, budgets and issues in one place.

I created this project to practice and demonstrate how Power BI can be used to turn project management data into something that is easier to track and understand.

## About the Project

Managing different projects usually means dealing with a lot of information at the same time — project status, milestones, activities, modules, budgets and issues.

The idea behind this dashboard was to bring these different areas together into a single interactive report.

The dashboard has three main pages:

- Overview
- Activity Analysis
- Project Details

Each page focuses on a different level of analysis, from an overall portfolio view to individual project details.

## What the Dashboard Shows

### Overview

The Overview page gives a quick picture of the complete project portfolio.

It includes information such as:

- Total number of projects
- Total project budget
- Overall milestone completion
- Project status
- Technology distribution
- Project activity trends

This page is mainly designed for getting a quick understanding of how the projects are progressing.

### Activity Analysis

The Activity page focuses more on day-to-day project execution.

It shows:

- Total activities
- Completed activities
- Blocked activities
- Activities on hold
- Activities in progress
- Not started activities
- Most active projects

This helps in understanding where project activity is happening and where work may be getting delayed.

### Project Details

The Project Details page allows the user to look at an individual project in more detail.

It includes:

- Project manager
- Technology
- Project status
- Project budget
- Budget completed
- Milestone completion
- Project health score
- Milestone progress
- Module-wise activity
- Module task completion
- Issue log
- Activity status

The project-level view is useful when more detailed analysis is required instead of looking at the complete portfolio.

## Data Used

The dataset contains sample project management information covering:

- Projects
- Milestones
- Modules
- Daily activities
- Issues

The data was created and structured for portfolio purposes, so it can be shared publicly without using confidential company information.

## Data Cleaning and Transformation

I used Power Query to prepare the data before building the dashboard.

Some of the main steps included:

- Cleaning the source data
- Standardising data types
- Renaming columns
- Removing unnecessary transformation steps
- Mapping module and milestone IDs
- Combining related information
- Preparing the tables for the Power BI data model

## Data Model

The model connects projects with their milestones, modules, activities and issues.

The main tables used in the project are:

**Project_Master**

Contains the main information about each project.

**Milestones**

Contains milestone names, status and project relationships.

**Modules**

Contains module-level information associated with milestones.

**Daily_Activity**

Contains daily project activity records and their status.

**Issue_Log**

Contains issues associated with project milestones.

I used relationships between these tables to make the dashboard interactive and allow filters to flow through the model.

## DAX

DAX was used to create the main KPIs and calculations used throughout the dashboard.

For example:

```DAX
    Total Activities =
    COUNTROWS(Daily_Activity)
    
    Milestone completion is calculated dynamically based on completed milestones:
    
    Milestone Completion % =
    DIVIDE(
        CALCULATE(
            COUNTROWS(Milestones),
            Milestones[Milestone_Status] = "Completed"
        ),
        COUNTROWS(Milestones),
        0
    )
```

I also used TREATAS() for some module-level calculations where the activity data needed to be connected through the module-to-milestone mapping.

Tools I Used

- Power BI
- Power Query
- DAX
- Excel
- Data Modelling
- Data Cleaning
- Dashboard Design

What I Practiced Through This Project

While building this dashboard, I worked on several areas of Power BI that are useful in real-world analytics projects.

This included:

- Creating an analytical data model
- Cleaning data using Power Query
- Creating DAX measures
- Working with relationships
- Building interactive visuals
- Designing KPI cards
- Creating drilldown-style project analysis
- Handling data mapping between tables
- Improving dashboard layout and usability
- Repository

The Power BI file and supporting project files are included in this repository.
The repository will also contain the sample dataset, dashboard screenshots and project documentation.
If you find the project useful or have any suggestions, feel free to explore the dashboard and the files in this repository.


Author

Devansh Khandal

Data Analytics | Power BI | SQL | Python | Advanced Excel



