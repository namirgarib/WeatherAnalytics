# 🌤 Weather Data Analysis and Visualization

This repository contains scripts and tools for processing and analyzing weather data. The data is extracted, processed, and visualized from various metrics across multiple cities and years.

## ℹ️ About
This project is a part of our assigment on **"Big Data Processing"** using shell script. It focuses on extracting, processing, and visualizing comprehensive weather data across multiple metrics and cities.

### Team Members
- [**Namir Garib**](https://github.com/namirgarib)
- [**Takumi Oyamada**](https://github.com/takumi0706)
- **Shunsuke Shimura**

⚠️ This repository contains my part of the assignment. For other part of the assignment, please visit the other repository [here](#).


## 🔔 Important Note

The scripts and instructions in this repository are configured based on the directory structure and file paths used during development. The paths in the scripts (e.g., `../data/`, `../weather_metrics/`) point to specific locations and datasets that may differ from your setup.

To ensure the scripts work correctly, you must update the file paths and directory locations in the scripts to match your environment. For example:

- Replace `INPUT_FILE` paths with the path to your input data file(s).
- Modify `OUTPUT_FOLDER` paths to match your desired output directories.
- If you're using a different dataset structure, adjust the column numbers used in the `awk` commands accordingly.

Failure to make these adjustments may result in errors or incorrect outputs. Please review and modify the scripts as needed for your data and file structure.

## 🚀 Features

1. 🔍 **Data Extraction**:
   - Extracts specific city data from comprehensive weather datasets.
   - Filters rows based on specific flags to ensure data accuracy.
   - Outputs results into neatly formatted CSV and TXT files.

2. 📊 **Data Processing**:
   - Calculates annual average temperature, mean daily minimum, and maximum temperatures.
   - Computes wind speed, relative humidity, sunshine hours, and precipitation totals.
   - Handles large datasets efficiently by minimizing redundant traversals.

3. 📈 **Visualization**:
   - Generates bar charts for weather metrics (temperature, wind, humidity, sunshine, and precipitation).
   - Sorts data by values and creates visually appealing horizontal bar charts.
   - Saves charts in high-resolution PNG format with labeled axes and descriptive titles.

4. 📏 **Metrics and Units**:
   - **Temperature**: Celsius
   - **Wind Speed**: m/s
   - **Humidity**: Percentage
   - **Sunshine**: Hours
   - **Precipitation**: mm

## 📂 File Structure

### 🗂 Input Files
- **Weather Data**: Located in the `../data/` directory.
- **City Metadata**: `obs_list.csv` and `places.txt` for city and station information.

### 📂 Output Files
- **Processed Data**: Saved in the `../weather_metrics/comprehensive/` directory.
- **Visualization Charts**: Saved in `../weather_metrics/bar_charts/`.

### 📜 Scripts
- `process_weather.sh`: Extracts and processes data for specified cities.
- `plot.py`: Generates bar charts from processed weather data.

## ⚙️ How to Run

### 🛠 Prerequisites
- Install the required dependencies:
  - **Python 3.8+**
  - Libraries: `matplotlib`, `csv`, `os`, `glob`
- Bash (for `.sh` scripts)

### 🏃‍♂️ Running Data Processing
1. Ensure the input data is placed in the `../data/` directory.
2. Update the list of places in `places.txt`.
3. Run the data processing script:
   ```bash
   ./process_weather.sh

### 🖼 Generating Visualizations
1. Run the Python plotting script:
```zsh
python3 plot.py
```

## 🎨 Example Output Format

### Processed Data (TXT)
```plaintext
2012 14.9 11.5 18.7 7.3 3.8 71 1832.2 2675.5
```

### Visualizations
Bar charts with:
- X-axis: Corresponding units for the metric
- Y-axis: Sorted city names
- Title reflecting metric and year

## 🗝 Key Scripts and Details

- `01_extract_places.sh`:
  Extracts specific city and station information from the comprehensive metadata file. Outputs a filtered list of places (`places.txt`) containing AMEDAS Observation Number and Ground Station Observation Number along with city names in the required format.

- `02_extract_data.sh`:
  Processes raw weather data files for all years and extracts data for the cities specified in `places.txt`. Handles filtering based on data quality flags and outputs processed data for each city into individual files.

- `03_normalize_data.sh`:
  Normalizes the extracted weather data to ensure all metrics are on comparable scales. Outputs the normalized data for each city and year, which is used for further analysis and visualization.

- `04_best_weather_score.sh`:
  Calculates an overall "best weather score" for each city based on normalized metrics. Aggregates scores using predefined weights for various metrics (e.g., temperature, wind, sunshine) and outputs rankings for all years.

- `05_other_weather_metrics.sh`:
  Processes additional weather metrics (e.g., average wind speed, humidity, sunshine hours, precipitation) for each city. Outputs annual summaries and rankings for individual metrics to support deeper analysis and visualization.
## 📐 Units and Descriptions

- Temperature (°C): Daily and annual averages.
- Wind Speed (m/s): Daily and annual averages.
- Humidity (%): Annual average of daily relative humidity.
- Sunshine Hours: Total hours of sunshine per year.
- Precipitation (mm): Total precipitation per year.

## 👤 Author

**Namir Garib**  
🎓 Student at Kanazawa University  
📧 Contact: [namir.garib@gmail.com](mailto:namirgarib@gmail.com)  
💻 GitHub: [NamirGarib](https://github.com/namirgarib)  
🌐 Website: [Namir Garib](https://www.namirgarib.com) 

### 🛠 Contributions
- Developed tools and scripts for processing, normalizing, and analyzing weather data.
- Designed efficient algorithms for calculating weather metrics, including best weather scores and detailed annual summaries.
- Integrated visualization tools for presenting weather trends across multiple years and locations.