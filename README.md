# Spotify Most Streamed Songs 2023 Dashboard Project

# Overview

This project analyzes the Spotify Most Streamed Songs 2023 dataset to uncover trends in music streaming, artist performance, and song characteristics. As a data analyst, I cleaned the dataset, created a custom calendar measure in Power BI, and developed an interactive dashboard to visualize key metrics such as streaming counts, playlist inclusions, and song attributes like danceability and energy. The dashboard provides actionable insights into top-performing songs, artist collaborations, and temporal trends, demonstrating my proficiency in data cleaning, measure creation, and data visualization.

# Dataset

The dataset, Spotify Most Streamed Songs 2023 Dataset .xlsx, contains 943 records of songs streamed on Spotify in 2023. It includes attributes such as track_name, artist(s)_name, artist_count, released_year, released_month, released_day, streams, in_spotify_playlists, in_spotify_charts, bpm, danceability_%, energy_%, and more. The dataset captures songs from various artists, release dates, and musical characteristics, providing a rich foundation for analysis.

# Measure Creation in Power BI

I created a custom calendar table and measures in Power BI to enable temporal analysis and derive meaningful metrics:

Calendar Table:

Generated a calendar table to cover the range of released_year (1975–2023).

Added columns for Year, Month, Quarter, and MonthName for time-based aggregations.

Calendar = 
ADDCOLUMNS(
    CALENDAR(MIN('spotify-2023'[Date]), MAX('spotify-2023'[Date])),
    "Year", YEAR([Date]),
    "Quarter", QUARTER([Date]),
    "Quarter(Q)", FORMAT([Date], "\QQ"),
    "Month", MONTH([Date]),
    "MonthName", FORMAT([Date], "mmm"),
    "Day of Week", WEEKDAY([Date]),
    "DayName", FORMAT([Date], "dddd")
)

Established a relationship between the release_date in the Spotify dataset and the Date column in the calendar table.

This measure facilitated dynamic temporal and categorical analysis in the dashboard.

# Dashboard Creation in Power BI

I designed an interactive Power BI dashboard to visualize the cleaned data and measures:
Total Streams: Displayed as "141.5B" for an overview of streaming volume.

Songs by Release Year: A line chart showing the number of songs released each year, with a peak in 2022 (e.g., 346 songs).

Top 10 Songs by Streams: A bar chart highlighting songs like "Blinding Lights" by The Weeknd (3.7B streams) and "As It Was" by Harry Styles (2.5B streams).

Artist Collaboration Impact: A scatter plot comparing artist_count vs. streams, showing that songs with 2 artists (e.g., "Ella Baila Sola" by Eslabon Armado and Peso Pluma, 725M streams) often perform well.

Danceability vs. Energy: A scatter plot illustrating the relationship between danceability_% and energy_%, with most popular songs clustering around 60–80% for both metrics.

Streams by Month of Release: A bar chart using the calendar table to show streaming trends by release month, with March 2023 having the highest streams (e.g., 15.2B).

Slicers: Added filters for released_year, artist(s)_name, and key to enable user interaction.

The dashboard features a modern design with a light theme, clear labels, and tooltips for detailed insights.

# Key Insights

Streaming Dominance: "Blinding Lights" by The Weeknd leads with 3.7B streams, followed by "As It Was" by Harry Styles (2.5B), indicating strong listener preference for pop hits.

Temporal Trends: 2022 was the most prolific year for streamed songs (346 songs), reflecting a surge in releases that gained traction in 2023.

Collaboration Impact: Songs with 2 artists average higher streams (e.g., 650M for duets vs. 500M for solo artists), suggesting collaborations boost popularity.

Musical Characteristics: High-streaming songs typically have danceability_% and energy_% between 60–80%, as seen in hits like "Flowers" by Miley Cyrus (71% danceability, 68% energy).

Release Timing: Songs released in March 2023 (e.g., "Ella Baila Sola") garnered the highest streams (15.2B), possibly due to spring promotional campaigns.

Interesting Fact: Despite the dataset spanning 1975–2023, the oldest song, "Riptide" by Vance Joy (1975), still amassed 2B streams, highlighting the timeless appeal of certain tracks in the streaming era.

These insights demonstrate my ability to derive actionable trends from complex datasets.
