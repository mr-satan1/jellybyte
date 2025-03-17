# Jellybyte - LLM-Powered Threat Intelligence Research Lab

Jellybyte is a ready-to-use platform that simplifies threat intelligence research using Large Language Models (LLMs). With pre-configured containers for JupyterLab and Open-WebUI, you can quickly dive into analysis without complex setup. Compatible with Apple Silicon or Nvidia GPU's!

It includes a suite of popular Python libraries for threat analysis enabling immediate use for threat research, malware analysis, and incident response.

| Library        | Description                                                                                   | Use in Threat Intelligence                              |
|----------------|-----------------------------------------------------------------------------------------------|---------------------------------------------------------|
| `ollama`       | A library for interacting with large language models (LLMs) for generating responses.         | Used for querying LLMs to extract or generate threat intel. |
| `pyjarm`       | A tool for extracting and analyzing JAR file contents, commonly used in malware analysis.     | Useful in reverse engineering and analyzing Java-based malware. |
| `requests`     | A popular HTTP library for making API requests and interacting with web services.             | Used for gathering data, querying APIs, or scraping threat intel from web sources. |
| `pyattck`      | A Python client for working with the MITRE ATT&CK framework.                                  | Helps in mapping and analyzing adversary tactics and techniques. |
| `pandas`       | A library for data manipulation and analysis, especially for structured data (e.g., CSV, JSON).| Used to process and analyze structured threat intel data. |
| `numpy`        | A library for numerical computing, often used for data analysis and machine learning.         | Useful in processing threat data, especially in analysis of large datasets. |
| `stix2`        | A library for working with STIX 2.0 threat intelligence data format.                          | Enables the creation and manipulation of structured threat intelligence. |
| `yara-python`  | A Python binding for YARA, used in malware analysis and detection.                            | Used for creating and applying YARA rules to detect known malware. |
| `volatility3`  | A tool for memory forensics, useful in incident response and reverse engineering.             | Used to analyze memory dumps for signs of compromise or malware. |
| `matplotlib`   | A plotting library for creating visualizations of data.                                       | Used for creating charts and graphs to visualize threat data trends. |
| `seaborn`      | A data visualization library based on `matplotlib` that simplifies statistical plots.         | Helps in visualizing complex threat data in an easy-to-understand format. |
| `scipy`        | A library for scientific computing, including optimization and statistical functions.         | Useful for advanced statistical analysis and mathematical operations in threat research. |
| `pefile`       | A Python library for parsing and analyzing Windows PE (Portable Executable) files.            | Used in malware analysis to inspect and manipulate Windows executables. |
| `cpe`          | A library for working with Common Platform Enumeration (CPE) identifiers.                     | Helps track vulnerabilities associated with specific software and hardware platforms. |
| `pycti`        | A Python client for integrating with the Open Cyber Threat Intelligence Platform (OpenCTI).   | Enables integration with OpenCTI to gather and share threat intelligence. |
| `bro`          | Python bindings for Zeek (formerly Bro), used for network traffic analysis.                   | Helps analyze network traffic logs and detect potential security threats. |
| `opencsv`      | A simple CSV file parsing and writing library.                                                | Used for handling CSV-formatted threat intelligence data. |
| `pymisp`       | A Python client for interacting with MISP (Malware Information Sharing Platform).             | Used for sharing and receiving threat data via the MISP platform. |


Note - this is all a local LLM stack using JupyterLabs, Ollama and OpenWebUI.

## Prerequisites

- Ensure you have [Docker](https://www.docker.com/get-started) and [Docker Compose](https://docs.docker.com/compose/install/) installed on your local machine.
- Ensure you have an internet connection to download the models.
- [Apple Silicon Users] - Make sure you have [Ollama](https://www.ollama.com) installed and running on the default host/port.

## Steps to Get Started

### Step 1: Clone the Repository

Start by cloning this repository (or downloading it) to your local machine.

```bash
git clone https://github.com/mr-satan1/jellybyte
cd jellybyte
```

### Step 2: Build the Docker Containers
In the root of the repository, where the docker-compose.yml file is located, run the following command to build the necessary Docker containers:
```bash
# For Apple environments
docker compose -f docker-compose-apple.yml up --build

# For Nvidia environments
docker compose -f docker-compose-nvidia.yml up --build
```


### Step 3: Start the Docker Containers
Once the containers are built, you can bring up the entire setup using the following command:

```bash
docker compose up -f ${your_env_of_choice}.yml 
```

### Step 4: Login to Open-WebUI and Select a Model
After the containers are up and running, follow these steps:

1. Open your browser and go to Open-WebUI (should be http://localhost:8080)
2. In Open-WebUI, log in and navigate to the "Model" section.
3. Select Llama 3.2 (or another model you want to use) and click the Download button.

Make sure you have enough disk space for the model. It may take some time to download.

### Step 5: Access JupyterLab
1. Open your browser and go to JupyterLab (should be http://localhost:8888)
2. When prompted for a token, use the token defined in the docker-compose.yml file. You can find it under the JUPYTER_TOKEN environment variable. The default token is *jellybyte*.

### Step 6: Use the Provided Notebook (example.ipynb)
Once you're in JupyterLab:

1. Navigate to the "notebooks" directory.
2. Open the example.ipynb file.
3. Run the cells in the notebook to interact with the LLM model (in this case, Llama 3.2).

### Step 7: Save Your Research
* All notebooks you create will be saved persistently in the 'notebooks' folder.
