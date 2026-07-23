# Netflix Content Analysis Dashboard
<img width="1237" height="745" alt="image" src="https://github.com/user-attachments/assets/64e0abb3-b89e-4ddf-8e92-8d3aeddc72bd" />
<img width="1243" height="746" alt="image" src="https://github.com/user-attachments/assets/5d3c0369-fab2-4b40-a1f7-2def5c98bba8" />


This repository contains a Microsoft Power BI project that provides a comprehensive and interactive dashboard for analyzing the Netflix movie and TV show dataset. The dashboard offers insights into content trends, distribution, and details of individual titles.

## Features

*   **Interactive Visualizations:** The dashboard is built with a variety of engaging charts and maps to explore the Netflix library.
*   **Dual-View Analysis:** Two distinct report pages for different analytical purposes:
    *   **Overview:** A high-level summary of content trends, including growth over time, genre popularity, rating distributions, and geographic availability.
    *   **Single Title Drill-Down:** A detailed view for a specific movie or TV show, showing its cast, director, description, and more.
*   **Structured Data Model:** Connects to a MySQL database, with a well-defined semantic model linking titles, cast, directors, genres, and countries.

## Dashboard Pages

### 1. Overview

The "Overview" page provides a macro-level view of the entire Netflix dataset. It helps in understanding broad trends and patterns.

*   **Shows Added by Date:** An area chart visualizing the volume of content (Movies vs. TV Shows) added to the platform over the years.
*   **Shows by Rating:** A column chart that breaks down the number of titles available for each content rating (e.g., TV-MA, PG-13).
*   **Top 10 Genres:** A horizontal bar chart displaying the most common genres across the platform.
*   **Countries Available:** A world map that visualizes the number of titles available in each country, with larger bubbles indicating a greater content library.

### 2. Single Title View

This page allows you to dive deep into the specifics of any single title from the dataset.

*   **Title Selector:** A dropdown menu to search for and select a specific movie or TV show.
*   **Key Metrics:** Informative cards display the selected title's **Release Year** and **Rating**.
*   **Detailed Information:**
    *   A card displays the full **Description** of the title.
    *   Scrollable lists show the full **Cast**, **Director(s)**, and **Genres** (`Listed in`).
*   **Countries Available:** A map highlights the specific countries where the selected title is available for streaming.

## Technical Details

*   **Tool:** Microsoft Power BI Desktop
*   **Project Format:** Power BI Project (`.pbip`)
*   **Data Source:** The semantic model is configured to connect to a local MySQL database (`127.0.0.1:3306`) named `netflix_data`.

### Data Model

The dashboard is powered by a semantic model consisting of the following tables, linked primarily by `show_id`:
*   `netflix_titles`: The main table containing core information like title, type, release year, and rating.
*   `netflix_cast`: Links titles to their cast members.
*   `netflix_directors`: Links titles to their directors.
*   `netflix_listed_in`: Contains the genre classifications for each title.
*   `countries_released`: Maps titles to the countries where they are available.
*   `description`: Contains the plot summary for each title.

## How to Use

1.  **Prerequisites:**
    *   **Power BI Desktop:** Ensure you have a recent version installed.
    *   **MySQL Database:** Set up a local or remote MySQL server with the `netflix_data` database and the corresponding tables. The original dataset can be found on platforms like Kaggle.
2.  **Clone the Repository:**
    ```bash
    git clone https://github.com/kulaswad/netflix-dashboard.git
    ```
3.  **Open the Project:**
    *   Navigate to the cloned directory.
    *   Open the `NetFlix Dashboard.pbip` file with Power BI Desktop.
4.  **Configure Data Source:**
    *   Once the project is open, you will likely be prompted to configure the data source connection.
    *   Go to `Transform data` -> `Data source settings`.
    *   Select the MySQL data source and click `Change Source...`.
    *   Update the Server and Database details to match your MySQL setup.
    *   Provide the necessary credentials to connect.
5.  **Refresh Data:**
    *   After configuring the connection, click the **Refresh** button on the Home ribbon in Power BI Desktop to load the data from your database into the model.
