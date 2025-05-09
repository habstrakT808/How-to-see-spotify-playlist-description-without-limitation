# 🎵 Spotify Playlist Extractor

[![Python Version](https://img.shields.io/badge/python-3.6+-blue.svg)](https://www.python.org/downloads/)
[![Spotipy Version](https://img.shields.io/badge/spotipy-2.19.0-green.svg)](https://github.com/plamere/spotipy)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

Extract complete information from your Spotify playlists including descriptions, owner details, and comprehensive track metadata using the Spotify Web API.

## 📋 Features

Have u had a problem like this ?

![Image](https://github.com/user-attachments/assets/eb46f184-e360-4e81-b09c-d1f07de765c3)

Now, watch the step carefully and try this trick. It's 100% works! You will have features like this :

- Extract complete playlist information including description, name, and owner
- Get detailed track information for all songs in a playlist
- Export data to CSV for easy analysis in spreadsheet applications
- Save playlist info as JSON for programmatic use
- Support for playlists of any size (handles pagination)

## 🔧 Prerequisites

- Python 3.6+ (Google Collab - Highly Reccomended)
- Spotify account
- Spotify Developer credentials

## 🔑 Setting Up Spotify Developer Account

### Step 1: Create a Spotify Developer Account

1. Visit [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/) and log in with your Spotify account

### Step 2: Create a New Application

1. Click the **Create App** button
2. Fill in the application details:
   - **App name**: Enter a name for your application (e.g., "My Playlist Extractor")
   - **App description**: Brief description of your app (e.g., "Application to extract Spotify playlist information including descriptions and metadata")
   - **Redirect URI**: Enter `http://127.0.0.1:8000/callback` (this is where users will be redirected after authentication)
   - **Which API/SDKs are you planning to use?**: Select "Web API"
   - Check the terms of service agreement box
3. Click **Save**

Example :

![Image](https://github.com/user-attachments/assets/43575a42-ecab-4516-991a-fda08bcad55f)

![Image](https://github.com/user-attachments/assets/ed6efe58-7ace-4c2c-85a3-5a758917ca27)

### Step 3: Get Your Credentials

1. After creating your app, you'll be taken to the app's dashboard
2. Note your **Client ID** (visible on the dashboard)
3. Click **View Client Secret** to reveal and copy your Client Secret
4. Keep these credentials secure - you'll need them to authenticate with the Spotify API

## 🚀 Usage

Run the script on your own google collab :

```bash
How-to-see-spotify-playlist-description-without-limitation.ipynb
```

Follow the prompts:

1. Enter the URL or ID of the Spotify playlist you want to extract
2. View basic playlist information
3. Choose whether to download full track data
4. Select output format (CSV and/or JSON)

### Example Output

The script will generate some information and two files:

![Image](https://github.com/user-attachments/assets/3d6f6aa6-dfa7-4974-b4f6-bdb71d7cc191)

1. `playlist_data.csv`: Contains all track information with playlist metadata
2. `playlist_info.json`: Contains detailed playlist information

## 📊 Data Analysis

Once you have exported your playlist data, you can:

- Open the CSV file in Excel, Google Sheets, or any spreadsheet software for analysis
- Use the JSON data in other applications or scripts
- Analyze trends in your music taste
- Discover your most played artists and albums

## 🔍 Example Code

Here's a basic example of how the extraction works:

```python
import spotipy
from spotipy.oauth2 import SpotifyClientCredentials

# Set up Spotify client
client_credentials_manager = SpotifyClientCredentials(
    client_id='your_client_id', 
    client_secret='your_client_secret'
)
sp = spotipy.Spotify(client_credentials_manager=client_credentials_manager)

# Get playlist information
playlist_id = 'spotify:playlist:37i9dQZF1DXcBWIGoYBM5M'  # Today's Top Hits
playlist = sp.playlist(playlist_id)

# Print basic information
print(f"Name: {playlist['name']}")
print(f"Owner: {playlist['owner']['display_name']}")
print(f"Description: {playlist['description']}")
print(f"Tracks: {playlist['tracks']['total']}")
```

## 📝 Limitations

- The Spotify Web API has rate limits that may affect large-scale data extraction
- In development mode, your application can access data for up to 25 Spotify accounts
- Some playlist metadata may be limited based on privacy settings

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

- [Spotipy](https://github.com/plamere/spotipy) - Python library for the Spotify Web API
- [Spotify for Developers](https://developer.spotify.com/) - For providing access to the Spotify API

---

Made with ❤️ by Hafiyan Al Muqaffi Umary
