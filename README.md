Anime Recommender 5.0 (MAL Rater Stats)
A robust, local anime recommendation web application featuring custom algorithm scoring, genre-based discovery, and seamless MyAnimeList (MAL) integration. Built to help you find exactly what to watch next without sifting through shows you've already seen.

This project is currently in active development. The repository showcases the architecture, custom scoring workflow, and core functionality.

✨ Features
Smart Discovery Engine: Filter by highly specific genres, themes, and demographics using AND/OR logic.

MAL Integration: Safely connect your MyAnimeList account (via local settings) to automatically exclude anime you've already watched or dropped.

Custom Algorithm: Ranks anime based on a weighted composite score of MAL ratings, global approval, and user engagement ratios.

Secure Authentication: Local user registration with password hashing and email verification (via Resend API, with local token fallback).

Automated Data Updates: Built-in scraper (database_updater.py) to pull the latest stats and shows from the Jikan API.

Developer Friendly: Includes a start.py utility script to handle virtual environments, dependencies, and database extraction automatically.

📸 Screenshots
(Replace these placeholder links with actual paths to your images once you take them!)

The main discovery dashboard and genre filtering interface.

Detailed, algorithmically sorted recommendation cards.

📂 Project Structure
Plaintext
├── frontend/
│   ├── index.html       # Main UI structure
│   ├── app.js           # Client-side logic & API calls
│   └── styles.css       # Custom styling and animations
├── server.py            # Main Python web server & API router
├── logic.py             # Recommendation engine and math algorithms
├── auth.py              # User authentication & email verification logic
├── database_updater.py  # Jikan API scraper to update the local DB
├── start.py             # Helper script for one-click local setup
├── config.py            # Global variables and genre mapping
├── anime_database.json.gz # Compressed baseline anime database
└── .env.example         # Template for environment variables
🚀 Run Locally
1. Configure Environment
Copy the example environment file and fill in your details:

Windows Command Prompt:

DOS
copy .env.example .env
Mac/Linux/PowerShell:

Bash
cp .env.example .env
2. Install & Extract
Use the built-in helper script to automatically create a virtual environment, install dependencies, and unpack the database:

Bash
python start.py install
3. Start the Server
Launch the application:

Bash
python start.py run
If your browser doesn't open automatically, navigate to http://localhost:8080.

⚙️ Environment Variables
Add these to your .env file to customize your instance:

PORT — HTTP port override (Default: 8080)

MAL_CLIENT_ID — Your MyAnimeList API client ID (for fetching user lists).

MAL_USERNAME — Default MyAnimeList username to exclude from results.

RESEND_API_KEY — (Optional) Key for sending verification emails. If left blank, the app will display the token on-screen.

SITE_URL — Base URL used for verification links (Default: http://localhost:8080).

🗺️ Roadmap
[x] Basic web server and UI architecture

[x] Custom scoring algorithm and AND/OR filtering

[x] Local user authentication and secure password hashing

[ ] Implement user watchlists / "Save for later" feature directly in the app

[ ] Add advanced filtering (Studio, Year/Season, Voice Actors)

[ ] Create a Dockerfile for easier containerized deployment

📝 License
This project is licensed under the MIT License.
