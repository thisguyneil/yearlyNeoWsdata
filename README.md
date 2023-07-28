# YearlyNeoWsdata

A comparison of Near Earth Object (asteroids) using NASA's Near Earth Object Web Service API for the years 2021 and 2022. 


# Downloading and running:
This notebook has some requirements to get it to work, below are step by step instructions on to download this repository, create a virtual environment, install the required packages, and how to run the notebook in either Jupyter notebook using anaconda or VSCode. 

1. Clone the GitHub Repository:
   - Open the Terminal or Command Prompt on your computer.
   - Navigate to the directory where you want to store the repository using the "cd" command.
   - In the GitHub repository, click on the green "Code" button and copy the repository's URL (HTTPS or SSH).
   - In the Terminal, run the following command to clone the repository (replace <repository_url> with the link to the github repository you just copied):
     ```
     git clone <repository_url>
     ```
   - The repository will be cloned to your local machine.

2. Navigating to the Repository:
   - Use the "cd" command to navigate into the cloned repository's directory. For example:
     ```
     cd repository_folder
     ```
   - Now you are inside the repository's directory on your local machine.

3. Creating a Virtual Environment using venv:
   - In the Terminal, navigate to the root directory of the repository (where the "requirements.txt" file is located).
   - Check if you have Python installed by running the command:
     ```
     python --version
     ```
   - If Python is installed, create a virtual environment using venv by running the command:
     ```
     python -m venv venv
     ```
   - Activate the virtual environment:
     -- On Windows: 
       ```
       .\venv\Scripts\activate
       ```
     -- On macOS/Linux:
       ```
       source venv/bin/activate
       ```

4. Installing Required Packages from the requirements.txt file:
   - With the virtual environment activated, run the following command to install the required packages:
     ```
     pip install -r requirements.txt
     ```
   - This will install all the packages listed in the "requirements.txt" file into your virtual environment.

5. Opening the Python Notebook: There are two main ways to open this notebook. You can use jupyter notebook through anaconda, or you can open the notebook directly with VSCode. 

Here's how you can open the notebook using jupyter notebook:
   - After installing the required packages, ensure that the virtual environment is still activated.
   - Use the "cd" command to navigate to the location of the Python notebook within the repository.
   - Launch the Jupyter Notebook by running the following command:
     ```
     jupyter notebook
     ```
   - This will open a new browser window showing the contents of the repository. Navigate to the notebook file and click on it to open and start working with it.

If you are using VSCode, here's how you would use this notebook:
   - Launch Visual Studio Code on your computer.
   - Open the repository folder by selecting "File" > "Open Folder" and navigate to the cloned repository's directory (the one that contains the notebook file).
   - In the Visual Studio Code's terminal, ensure that the virtual environment is activated. If it's not already activated, activate it using the following commands:
     -- On Windows: 
       ```
       .\venv\Scripts\activate
       ```
     -- On macOS/Linux:
       ```
       source venv/bin/activate
       ```
   - Once the virtual environment is activated, you can open the Python notebook file in VSCode by either:
     -- Navigating to the notebook file in the file explorer and double-clicking it, or
     -- Using the "File" > "Open" option in VSCode and selecting the notebook file.
   
   - VSCode will now open the Python notebook, and it will automatically use the virtual environment you created for running the code and installing any required packages. When running the cells, if you have not used python notebook cells before in vscode, you may be asked to install an ipynb extension to run python notebook cells. This installation is required to run these cells. 


# Using the notebook

## The notebook is ready to use but certain features will require some changes to the code.

### 1. Getting our asteroid data.
This section contains a script to download both the 2021 and 2022 asteroid data. The section is mainly there to show how I downloaded my data and key parts to get it to work have been commented out. In the directory of this project, in the data folder, there are two folders for each year. The 'original' folder is the exact data I downloaded and included in case you didnt want to run the downloading script. The downloading script can take multiple minutes to fully complete depending on various things such as internet speed, computer hardware, etc.
#### **You do not have to download the data if you want to run the notebook. The rest of this project is designed to run off of the included data.**

If you decide to run the download script to download the data yourself, here's what you will need to do:
1. Open a web browser and go to https://api.nasa.gov/ 
2. Fill out the section called "Generate API Key"
3. You will be provided with an API key, make sure to save this API key either in a notes app, word doc, email it to yourself, etc. It would work best to have it saved on the computer you intend to run the script on so you can copy/paste easily. 
4. Both the 2021 and 2022 scripts include a line that will need to be changed. On the third line of each script is this:
```
# Remove this to use the API key: api_key = "*insert API key here*"
```
Read the line and follow the instructions. If, for example, your API key was "1234567" then you would change this line for each script to:
```
api_key = '1234567'
```
5. Once the data has been downloaded, it will be saved into the 'downloaded' folder for each year in the directory of this project. 
6. There are additional lines in this project that will be pulling files from the 'original' data folder. We will cover how to change those more in this readme.

### 2. Cleaning our NeoWs data
For this section, we have 2 different code blocks, one for each year, that reads in our json files and creates a dataframe for each year. By default, these blocks are reading in data from the 'original' data folder, if you download the data yourself then we need to change this over to the 'downloaded' data folder.
1. Towards the top of each code block for each year will be a line that looks like this:
```
for file_name in glob.glob('data/2021/original/*.json')
```
For both of these years, change the 'original' to 'downloaded', so the final product would look like:
```
for file_name in glob.glob('data/2021/downloaded/*.json')
```
Once you do this for both code blocks, then the code for the second section will read in the downloaded code instead. 

From here the rest of the script will load in the correct data and no other changes should be required. 
# Requirements met:
1. Read in TWO text data sources (in any format). For example, email chains or different pages from a book. 
2. Clean and operate on the data while combining them
3. Make 3 matplotlib or seaborn (or another plotting library) visualizations to display your data.
4. Utilize a virtual environment and include instructions in your README on how the user should set one up
5. Annotate your code with markdown cells in Jupyter Notebook, write clear code comments, and have a well-written README.md
6. Read TWO data sets in with an API (or use two different APIs that have data you can combine to answer new questions).