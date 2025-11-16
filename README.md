# Pyxis - Accident Prone Zone Mapping and Analysis

A Streamlit application for visualizing and analyzing accident data using interactive maps, clustering algorithms (K-means), and association rule mining (Apriori).

## Features

- **Upload and Map Data**: Visualize accident locations on interactive maps with heatmaps
- **Frequency Distribution**: Analyze categorical data with tables and graphs
- **K-means Clustering**: Apply clustering algorithms to discover accident patterns
- **Apriori Analysis**: Find association rules in accident data

## Keeping the App Alive

This repository includes a GitHub Actions workflow that automatically pings your Streamlit app to prevent it from sleeping on free-tier hosting platforms.

### Setup Instructions

1. **Deploy your Streamlit app** to Streamlit Cloud or another hosting platform

2. **Add the app URL as a GitHub secret**:
   - Go to your GitHub repository
   - Navigate to Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `STREAMLIT_APP_URL`
   - Value: Your deployed app URL (e.g., `https://your-app-name.streamlit.app`)
   - Click "Add secret"

3. **Enable GitHub Actions** (if not already enabled):
   - Go to the "Actions" tab in your repository
   - If prompted, click "I understand my workflows, go ahead and enable them"

4. **Verify the workflow is running**:
   - The workflow runs automatically every 25 minutes
   - You can also trigger it manually from the Actions tab → "Keep Streamlit App Alive" → "Run workflow"

### How It Works

- The workflow pings your app every 25 minutes
- This prevents the app from sleeping on platforms with 30-minute inactivity timeouts
- The workflow uses a GitHub secret to store your app URL securely
- You can monitor ping results in the Actions tab

## Local Development

### Requirements

Install dependencies:
```bash
pip install -r requirements.txt
```

### Running the App

```bash
streamlit run app.py
```

## Usage

1. Upload a CSV file containing accident data with columns like:
   - latitude, longitude
   - location, offense, date
   - cause of accidents, victims age, suspects age
   - victims gender, suspects gender
   - vehicle kind, time

2. Navigate through different views using the sidebar:
   - **Upload and Map Data**: View accident locations on an interactive map
   - **Frequency Distribution**: Analyze data distributions
   - **Apply kmeans**: Cluster accident data using K-means algorithm
   - **Apply apriori**: Discover association rules in the data

## License

This project is open source and available for use and modification.
