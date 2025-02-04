# Change Log
This change log provides version history for the Streamlit Dashboard.

View the Streamlit dasboard: https://streamlit.digitalghost.dev/

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

* **MAJOR:** Any changes to the backend infrastructure that requires new methods of moving data that won't work with the previous architecture, mainly with the addition of new databases or data sources.
* **MINOR:** Any changes to the Streamlit dashboard that adds a new interaction/feature or removal of one.
* **PATCH:** Any changes that fix bugs, typos or small edits.

## 2.11.0 | 2023-11-03

### Added
* Added an **About** tab to display information about the project and the author.

### Changed
* Changed the `stadiums_map()` function into an importable `Class`.

### Fixed
* Fixed the SQL responsible for populating the `st.dataframe` for **Standings** to order rows by `rank`.

### Removed
* Removed **Top Teams Movement** section from **Standings & Overview** tab.

## [2.10.3] | 2023-10-26

### Changed 
* Changed the `social_media()` function into an importable `Class` from the newly created `components/` directory. Importing as:

 `from components.social_media import SocialMediaSection`

## [2.10.2] | 2023-10-20

### Changed
* Changed social media icons into static `.svg` files instead of using Font Awesome icons.


## [2.10.1] | 2023-09-10

### Fixed
* Fixed the **News** tab to not error out when the table does not have at least 4 rows of data by implementing a `try/except` block.


## [2.10.0] | 2023-09-04

### Added
* Added club logo to the Standings `st.dataframe`.
* Added `st.subheader` under main header to display current round.
* Added **News** tab to display the latest news from the Premier League using the [News API](https://newsapi.org/).


## [2.9.1] | 2023-08-27

### Fixed
* Fixed the Standings column headers in the `st.dataframe` element to display proper column names instead of the SQL column names.


## [2.9.0] | 2023-08-20

### Added
* Added Docker logo to social media section with link to Docker Hub repository.
* Added `st.toast` to display a more subtle message to the user that the page is loading and when the data has loaded.
* Added a new `st.dataframe` table to display current total metrcis for the league (Goals Scored, Penalties Scored, and Clean Sheets).

### Changed
* Changed page title to **"Streamlit: Premier League"**.
* Changed tab names from **Standings** to **Standings & Overview** and **Statistics** to **Top Teams & Scorers**.
* Changed `st.data_editor` to `st.dataframe` for displaying the statistic tables.

### Fixed
* Fixed the `st.dataframe` tables under the **Top Teams Movement** section to display the correct data by sorting columns in descending order.

### Removed
* Removed `st.spinner`.


## [2.8.0] | 2023-08-12

### Added
* Added `st.spinner` to run when page loads to allow all tabs and data to load before a user can start navigating.
* Added type annotations to `standings_table()` function to return `DeltaGenerator`.
* Added type annotations to `stadiums_map()` function to return `DeltaGenerator`.

### Changed
* Changed `st.subheader` from "Standings" to "Current Standings".
* Changed `st.table` to `st.dataframe` for showing current standings.
* Changed `st.map` location from *Playground* to *Standings* tab.
* Changed the Social Media section to exist inside a function: `social_media()` and be called later in each tab.
* Changed the standings table code to exist inside a function: `standings_table()`.
* Changed the map code to exist inside a function: `stadiums_map()`.
* Changed the format of writing out the Top 5 Teams, Top 5 Scorers, and Forms for the Rest of the League sections to use a `for` loop instead of writing out each section individually.

### Fixed
* Fixed the date to correctly display the suffix of the number *(i.e. 1st, 2nd, 3rd, etc.)* and to remove leading zeroes for single digit dates.

### Removed
* Removed *Playground Tab*.
* Removed `pages/` directory as this app will continue development as a single page.
* Removed `style.css`, standings table is no longer stylized with CSS.
* Removed `st.slider` as interactive Streamlit elements in dashboards with tabs seemed to currently be bugged. 
    * Related issues: [#4996](https://github.com/streamlit/streamlit/issues/4996), [#6257](https://github.com/streamlit/streamlit/issues/6257), and [#7017](https://github.com/streamlit/streamlit/issues/7017).
* `st.bar_chart` has also been removed due to this bug.
* Removed `import os`, `import psycopg2`, `import plotly.graph_objects as go` as they are no longer needed.


## [2.7.1] | 2023-07-13

### Fixed
* **Main Page**, *Standings Tab*: Fixed `iloc[X][X]` values to match the correct column to pull in correct data for the Top 5 Teams section.


## [2.7.0] | 2023-07-12

### **Added**
* **Main Page**, *Standings Tab*: Added 3 `st.column_config.ProgressColumn` cards to display rankings of teams with the highest `penalties_scored`, `average_goals`, and `win_streak` during the season.

### **Changed** 
* **Main Pages**, *Standings Tab*: Changed the data values for `label` and `value` for the `st.metric` card.


## [2.6.0] | 2023-06-28

### **Added**
* **Playground Page**: Added social media icons to bottom of page.
* **Main Page**, *Statistics Tab*: Added `assists` metric to the *Top 5 Scorers Section*.
* **Main Page**, *Standings Tab*: Added a metric card to display the top 5 teams' position movement throughout the season.

### **Changed**
* **Main Page**: Changed  title to "2023-24" to reflect the new season.
* **Main Page**, *Fixtures Tab*: Changed ordering of `fixtures` to appear in chronological order.

### **Removed**
* **Main Page**, *Fixtures Tab*: Removed extra comma from `fixtures` date.


## [2.5.0] | 2023-06-19

### **Added**
* Added a new page: **Playground**, that holds graphs with slicers, filters, and other sortable features that allows the end user view statitics in a custom way.
* Added `Recent_Form` to `standings` table as a new column.
* Added string to display current date on **Standings** tab.

### **Changed**
* Changed page title from **Overivew** to **Premier League - Statistics, Scores & More**.
* Changed **Overview** tab name to **Standings**.

### **Removed**
* Removed map of stadium locations from **Main** page; moved it to the new **Playground** page.


## [2.4.0] | 2023-05-26

### **Added**
* Added number to *Top 5 Teams* section to indicate current rank.
* Added suffix to rank number in *Forms for the Rest of the League section*.

### **Changed**
* Changed hyperlink for GitHub icon to point to GitHub profile instead of repository for project. A link to GitHub repository already exists by default.

### **Fixed**
* Added `target="_blank" rel="noopener noreferrer"` to anchor elements to allow linked icons to open properly.


## [2.3.1] | 2023-05-25

### **Fixed**
* Fixed broken link for GitHub Icon on all tabs.


## [2.3.0] | 2023-05-24

### **Added**
* Added text that displays the final gameday of the season.
* Added linked icons to social media pages.

### **Changed**
* Changed tab title from **Top Teams & Top Scorers** to **Statistics**.


## [2.2.1] | 2023-05-19

### **Fixed**
* Fixed promotion/demotion legend by displaying items as a column instead of in a row.


## [2.2.0] | 2023-05-17

### **Changed**
* Changed the hex colors used for promtion/demotion status.
* Changed the color of `locations` map markers to `indigo` to match the rest of the theme.

### **Added**
* Added an extra color to denote europa conference league qualification promotion.
* Added solid border element to `standings` table to better denote promotion/demotion status.
* Added text under table to explain which color denotes which promotion/demotion status.


## [2.1.0] | 2023-05-10

### **Changed**
* Changed stadium `locations` map to use [plotly express](https://plotly.com/python/mapbox-layers/) `scatter_mapbox` instead of Streamlit's built in `st.map()` function.
    * This allows the stadium points to be hoverable which enables a tooltip that provides more information about the venue.
* Changed title to display ***Premier League Statistics / 2022-23*** instead of ***Premier League Statistics / '22-'23***.


## [2.0.2] | 2023-05-08

### **Fixed**
* Fixed the sorting of `rounds` to appear in decending order on the `fixtures` tab.


## [2.0.1] | 2023-05-05

### **Fixed**
* Adding '`<=`' to `while` loop to get the current round. Previously, the Streamlit app would only select rounds that were *less* than the `MAX` round which would omit the final round.


## [2.0.0] | 2023-05-02
Now using [Firestore](https://firebase.google.com/docs/firestore/) to store fixture data in a document format.

### **Added**
* Added `Fixtures` tab for all rounds in the current season. Updates 3 times a day and will add new rounds as they start.


## [1.3.0] | 2023-04-17

### **Added**

* Added page title.
* Added position number to teams in **Forms for the Rest of the League** section.

### **Fixed**

* Fixing capitalization for **Forms for the Rest of the League** subheader.

### **Removed**

* Removed Emojis from tab titles.


## [1.2.0] | 2023-04-16

### **Changed**

Top Teams Tab
* Renamed tab to: "⚽️ Top Teams & 🏃🏻‍♂️ Top Scorers".
* Changed `st.plotly_chart` to `st.line_chart`.
* Moved top scorers to this tab.

### **Removed**

Top Players Tab
* Removed this tab, combined with top teams tab.

## [1.1.0] | 2023-04-07

### **Added**

Top Teams Tab
* Added `logo` and `form` for the rest of the league.

### **Changed**

Top Teams Tab
* Center aligning `logo`, `form (last 5)`, `clean sheets`, `penalties scored`, and `penalties missed` in their containers.
* Setting `logo` width for top 5 teams to `150px`.

Top Players Tab
* Center aligning `photo`, `name`, `goals`, `team`, and `nationality` in their containers.
* Setting `photo` width for top 5 players to `150px`.

### **Removed**
* Removed `LIMIT 5` from SQL query to pull all teams.

## [1.0.0] | 2023-04-05

### **Added**

Overview Tab
* View the current standings for the league for the current season.
* An adjustable slider gives control to focus in on teams that fit within a certain number of points.
* A bar chart with teams (x-axis) and points (y-axis) adjusts accordingly to the slider.
* A map with plots for the stadium locations for each team in the current season.

Top Teams Tab
* Shows the `logo`, `form (last 5)`, `clean sheets`, `penalties scored`, and `penalties missed` for the current top five teams in the league.
* A line graph depicts the rise in points over each matchday.

Top Players Tab
* Shows the `portrait`, `goals`, `team`, and `nationality` of the current top five goal scorers in the league.

[2.10.3]: https://github.com/digitalghost-dev/premier-league/commit/c18d9bfaf762ba7c4c2714150c1f6cd0f722b9e8#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.10.2]: https://github.com/digitalghost-dev/premier-league/commit/53218cf868e3bc8128327932512f5ac1d28e6740#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.10.1]: https://github.com/digitalghost-dev/premier-league/commit/c2a0d39eb7cab1b7ed3013bb5811490f70bd256e#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.10.0]: https://github.com/digitalghost-dev/premier-league/commit/483e68208487c1632d2aa93ac098683a6c3515cc#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.9.1]: https://github.com/digitalghost-dev/premier-league/commit/a726d8fbf9f99bddc03a7fbf465ddba14ed97aee#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.9.0]: https://github.com/digitalghost-dev/premier-league/commit/d905a2a26b38200a519c78fa4e3847b598dc3d8f#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.8.0]: https://github.com/digitalghost-dev/premier-league/commit/ffc31af3ca6bc58294ab6c8c6daba105d9e7c1a5#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.7.1]: https://github.com/digitalghost-dev/premier-league/commit/a18341f802c46043fa8122c517e479103c067870#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.7.0]: https://github.com/digitalghost-dev/premier-league/commit/522600c0da5c6c20dd51528794bc959c1adcd9e3#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.6.0]: https://github.com/digitalghost-dev/premier-league/commit/de5b6c14e370ec08f0a79a2cc1dafd84a144411a#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.5.0]: https://github.com/digitalghost-dev/premier-league/commit/247029c3a94e607d5ffd2adabc41178647d1796e#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.4.0]: https://github.com/digitalghost-dev/premier-league/commit/19ff4063496a646aad3b8750a7c434cdeb1004e9#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.3.1]: https://github.com/digitalghost-dev/premier-league/commit/c11bfaa2f2aa0317783be65f935387e25cf180de#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.3.0]: https://github.com/digitalghost-dev/premier-league/commit/5e3cadd68cefef3abf7dbe1809257a9fae39af4a#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.2.1]: https://github.com/digitalghost-dev/premier-league/commit/903d457765df9de9d3a0ea879082dc0096bdbb38#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.2.0]: https://github.com/digitalghost-dev/premier-league/commit/11606ed57e6a4460d5059fc0141fbeccd268b716#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.1.0]: https://github.com/digitalghost-dev/premier-league/commit/f4e580d998e8e1042b9b824aa846bf3e738b3fd4#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.0.2]: https://github.com/digitalghost-dev/premier-league/commit/72337e2ac3ee365612a6a02eda25f390ab2690b9#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.0.1]: https://github.com/digitalghost-dev/premier-league/commit/dc92180f52a325f79e14d89097940162711ac35f#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[2.0.0]: https://github.com/digitalghost-dev/premier-league/commit/a8b11f02c8b517453c1d7d2e34b0986ea73588ba#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[1.3.0]: https://github.com/digitalghost-dev/premier-league/commit/4b2063a3663f48e166f7b13cbe06e51b24fd2056#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[1.2.0]: https://github.com/digitalghost-dev/premier-league/commit/8d5fbb7cdf91263eb55f2bc7ecd09236d975a704#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[1.1.0]: https://github.com/digitalghost-dev/premier-league/commit/e99f1f4a6eab3ef967c30b6c21b4fffa109de8e9#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d

[1.0.0]: https://github.com/digitalghost-dev/premier-league/commit/429a6f3ca12bcdbb5bee4505d390838b25edb8bb#diff-4dc66906e3c3b7f7a82967d85af564f2d5a6e0bee5829aa5eda607dd9756c87d