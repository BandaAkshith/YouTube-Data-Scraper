# YouTube Data Scraper

This project is a Python-based application for scraping data from YouTube videos using the YouTube Data API v3 and the YouTube Transcript API. It retrieves information about videos in a specified genre and saves the details to a CSV file. The application is flexible, dynamic, and designed to fetch data efficiently.

---

## Features

- **Dynamic Input**: Accepts a genre and the number of videos to fetch as user input.
- **YouTube Data API Integration**: Retrieves video metadata, including titles, descriptions, tags, and more.
- **Captions Handling**: Downloads captions (if available) using the YouTube Transcript API.
- **CSV Export**: Saves the video details to a timestamped CSV file.
- **Error Handling**: Handles quota limits, missing data, and transient errors gracefully.
- **Timezone Support**: Ensures timestamps in the CSV file are accurate for IST (Indian Standard Time).

---

## Installation

### Prerequisites

- Python 3.7 or later
- Google Cloud account for API key generation

### Required Libraries
Install the required libraries using pip:

```bash
pip install google-api-python-client youtube-transcript-api pandas pytz
```

---

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/youtube-data-scraper.git
   cd youtube-data-scraper
   ```

2. Set up your YouTube Data API key as an environment variable:
   - For Linux/Mac:
     ```bash
     export YOUTUBE_DATA_API_v3="YOUR_API_KEY"
     ```
   - For Windows (Command Prompt):
     ```cmd
     set YOUTUBE_DATA_API_v3=YOUR_API_KEY
     ```

3. Run the script:
   ```bash
   python scraper.py
   ```

4. Provide the following inputs when prompted:
   - **Genre**: The genre of videos to fetch (e.g., "music").
   - **Number of Videos**: The total number of videos to retrieve (e.g., 500).

5. The script will save the video details to a CSV file named in the format:
   ```plaintext
   GENRE_videos_YY-MM-DD_HH:MM:SS.csv
   ```
   Example: `music_videos_24-12-23_10:53:45.csv`

---

## Output

The CSV file contains the following fields:

- **Video URL**: Direct link to the video
- **Title**: Video title
- **Description**: Video description
- **Channel Title**: Name of the channel
- **Keyword Tags**: Video tags
- **YouTube Video Category**: Category ID of the video
- **Topic Details**: Relevant topic details
- **Video Published at**: Publish date of the video
- **Video Duration**: Length of the video
- **View Count**: Number of views
- **Comment Count**: Number of comments
- **Captions Available**: Whether captions are available
- **Caption Text**: Transcripts of the captions (if available)
- **Location of Recording**: Geographical location of the recording (if available)

---

## Error Handling

- **Quota Limits**: Displays a message if API quota is exhausted.
- **Missing Data**: Skips videos with incomplete or unavailable data.
- **Caption Errors**: Logs a warning if captions are not available or fail to download.

---

## Logging

The script uses the `logging` module to provide detailed logs for:
- API calls
- Video processing progress
- Errors and warnings

---

## Contributing

Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch for your feature/bug fix.
3. Commit your changes and submit a pull request.


