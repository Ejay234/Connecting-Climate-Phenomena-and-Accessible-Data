# Connecting Climate Phenomena and Accessible Data

**ENSO Analysis with OOI, ONC, and NEON Infrastructure**

**Author:** Ejay Aguirre
**Mentors:** Jeffery Glatstein & Jim Case

**DOI:** 10.5281/zenodo.16784160

### **Project Summary**

This project documents a reproducible workflow for analyzing the relationship between the El Niño-Southern Oscillation (ENSO) and local environmental data. By retrieving, cleaning, and visualizing temperature data from a variety of scientific infrastructures such as the Ocean Observatories Initiative (OOI), Ocean Networks Canada (ONC), and the National Ecological Observatory Network (NEON)—this repository demonstrates how to integrate disparate datasets to identify key climate trends. This work emphasizes the critical role of data and infrastructure literacy in modern scientific analysis.

### **Repository Contents**

This repository is organized into a series of Jupyter Notebooks, each focusing on a specific aspect of the data retrieval and analysis pipeline.

#### **1. `ENSO_Overlays.ipynb`**

This notebook serves as the foundation for the entire analysis.

* **Purpose:** To download and process the Oceanic Niño Index (ONI) data from NOAA.

* **Methodology:** The notebook reads the raw ONI data, converts seasonal codes to a common date format, and classifies each period as El Niño, La Niña, or Neutral.

* **Output:** The script generates a `segments` list that is used in the other notebooks to create the colored overlays on the plots, providing a visual context for ENSO events.

#### **2. `OOI_File.ipynb`**

This notebook focuses on oceanographic data from the OOI.

* **Purpose:** To retrieve, clean, and analyze sea water temperature data from OOI's Global Station Papa.

* **Methodology:** The notebook accesses data from NetCDF files, converts temperature units, removes outliers, and resamples the data to a monthly mean for comparability.

* **Key Insight:** The visualizations in this notebook demonstrate a clear correlation between ENSO events and ocean temperature fluctuations at this high-latitude site.

#### **3. `NEON_File.ipynb`**

This notebook explores terrestrial meteorological data from the NEON infrastructure.

* **Purpose:** To retrieve and analyze air temperature data from three specific NEON sites (ABBY, TEAK, PUUM) that were selected for their relevance to the project's geographic scope.

* **Methodology:** The notebook uses the NEON API to programmatically download data, which is then cleaned, converted to Fahrenheit, and resampled for plotting.

* **Note:** This notebook illustrates a successful data retrieval workflow, showing how to interact with the NEON API and handle its data products.

#### **4. `ONC_File.ipynb` and `ONC_Erddap.ipynb`**

These notebooks document the process of accessing data from Ocean Networks Canada.

* **`ONC_File.ipynb`:**

    * **Purpose:** To retrieve and analyze sea water temperature from ONC devices, such as those at Folger Deep and Barkley Canyon Upper Slope.

    * **Methodology:** This notebook uses the direct ONC API and is the primary source for the ONC data analysis in the final project.

* **`ONC_Erddap.ipynb`:**

    * **Purpose:** This is an exploratory notebook that documents an alternative approach using the ERDDAP API.

    * **Lessons Learned:** This method was ultimately not used due to complexities in data parsing, inconsistencies in data availability, and API quirks. The notebook is preserved as a record of the research process and a guide for others on potential challenges.

### **Methodology and Key Findings**

The overall methodology involved a clear pipeline from data retrieval to analysis and visualization. The key lesson learned was the importance of **data infrastructure literacy** where understanding the nuances of each data provider's API is as crucial as the scientific analysis itself. The project found that while higher-latitude sites exhibited weaker short-term ENSO signals, they showed clearer long-term cycles, and that the depth and resolution of the data were significant factors in identifying these trends.

### **How to Run the Project**

1.  **Clone the Repository:**

    ```bash
    git clone https://github.com/Ejay234/Connecting-Climate-Phenomena-and-Accessible-Data.git
    cd Connecting-Climate-Phenomena-and-Accessible-Data
    ```

2.  **Install Dependencies:**
    Use the provided `requirements.txt` file to install all necessary libraries with pinned versions for reproducibility.

    ```bash
    pip install -r requirements.txt
    ```

3.  **ONC API Token:**
    Some notebooks require an ONC API token. Make sure you have your token set up locally as a variable in your environment or within the notebook itself, if you are working privately.

4.  **Run the Notebooks:**
    Launch Jupyter and open the notebooks in the recommended order (`ENSO_Overlays.ipynb`, followed by the other notebooks) to see the full data pipeline.

    ```bash
    jupyter notebook
    ```

### **Acknowledgements**

**Mentors:**

* **Jeffery Glatstein** – Woods Hole Oceanographic Institution

* **Jim Case** – Woods Hole Oceanographic Institution

**Funding & Program Support:**

* U.S. National Science Foundation, Grant #2127548

* CI Compass
