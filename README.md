# NNN
Nerd Nurturing Network

# Table of Contents
[Repository Purpose](#what-is-this-repository-for)

[Original AdventureWorks](#original-adventureworks-2022)

[Current AdventureWorks](#current-adventureworks-2022)

[Software Requirements](#software-prerequisites)

* [Visual Studio](#visual-studio-2022)
* [SQL Server 2022](#sql-server-2022)

[GitHub Usage](#github-usage)

[SQL Best Practices](#sql-best-practices)

## What is this repository for?
This repository is for practicing sharing code relating to SQL projects and supporting the Nerd Nurturing Network. You will find the database that we're using in one of two forms: 
1. Original AdventureWorks 2022 database. If you want to work through all of the different queries and projects, this is the version you will want to download.
2. Current AdventureWorks 2022 database. If you would like to see where things are at, currently, with all changes that we discuss, this is the version you will want to download.

## Original AdventureWorks 2022
We will be using the version available here: https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2022.bak

For instructions on how to install this on your home PC: https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms

## Current AdventureWorks 2022
We will add this once we have made any changes.

# Software Prerequisites

## Visual Studio 2022
Here are the step-by-step instructions to download and install Visual Studio 2022 Community Edition:

#### Step 1: Download Visual Studio Installer
1. Open your web browser and go to the official Visual Studio download page:
   `https://visualstudio.microsoft.com/vs/community/`
2. Click on the "Free download" button under Visual Studio Community 2022.
3. The Visual Studio Installer setup file (`vs_installer.exe`) will be downloaded to your computer.

#### Step 2: Run the Visual Studio Installer
1. Once the download is complete, locate the `vs_installer.exe` file in your downloads folder.
2. Double-click the setup file to run the Visual Studio Installer.

#### Step 3: Start the Installation Process
1. The Visual Studio Installer will open and start downloading the necessary files.
2. Once the download is complete, you will be presented with the Workloads selection screen.

#### Step 4: Select Workloads
1. On the Workloads screen, select the workloads you want to install.
   * **Data Storage and Processing** This is the only workload required for our needs.
   * ![image](https://github.com/Clanatk/NNN/assets/33404493/7705e83d-7e80-4b1a-ad10-d63be4fc023d)
3. You can select other workloads based on your needs.

#### Step 5: Individual Components (Optional)
1. If you need specific individual components, click on the "Individual components" tab.
2. Select any additional components you need, such as .NET SDKs, language packs, etc.

#### Step 6: Installation Location
1. Click on the "Installation locations" tab to specify the installation path if you want to change it from the default location.
2. You can also specify where to download cache files.

#### Step 7: Install Visual Studio
1. Once you have selected the desired workloads and components, click the "Install" button.
2. The installer will begin downloading and installing the selected components. This process may take some time depending on your internet speed and the components selected.

#### Step 8: Sign In (Recommended)
1. After the installation is complete, you will be prompted to sign in with a Microsoft account. This step is optional but recommended to unlock additional features and synchronize settings.
2. If you choose not to sign in, click "Not now, maybe later."

#### Step 9: Start Visual Studio
1. Once the installation is complete and you have signed in (or skipped the sign-in), Visual Studio will launch.
2. You can start creating or opening projects from the Visual Studio start page.

## SQL Server 2022
#### Step 1: Download SQL Server 2022 Developer Edition
1. Go to the official Microsoft download page: 
   `https://www.microsoft.com/en-us/sql-server/sql-server-downloads`
2. Scroll down to the "SQL Server 2022 Developer" section.
3. Click on the "Download now" button to download the setup file.

#### Step 2: Run the SQL Server Installation
1. Once the download is complete, locate the downloaded file (usually named `SQL2022-SSEI-Dev.exe`) in your downloads folder.
2. Double-click the setup file to run the installer.

#### Step 3: SQL Server Installation Center
1. The SQL Server Installation Center will open. Click on the "New SQL Server stand-alone installation or add features to an existing installation" option.

#### Step 4: Accept License Terms
1. Read and accept the license terms by checking the box.
2. Click "Next" to continue.

#### Step 5: Install Setup Files
1. The installer will check for the latest updates and install the setup files. This may take a few minutes.
2. Once complete, click "Next."

#### Step 6: Choose Installation Type
1. Select the "New SQL Server stand-alone installation" option.
2. Click "Next."

#### Step 7: Feature Selection
1. In the Feature Selection window, select the features you want to install. For a basic installation, ensure the following features are selected:
   - Database Engine Services
   - SQL Server Replication
   - Full-Text and Semantic Extractions for Search
2. Click "Next."

#### Step 8: Instance Configuration
1. Choose the default instance or specify a named instance. For most users, the default instance is sufficient.
2. Click "Next."

#### Step 9: Server Configuration
1. In the Server Configuration window, set the SQL Server Database Engine to use the default account (usually `NT SERVICE\MSSQLSERVER`).
2. Click "Next."

#### Step 10: Database Engine Configuration
1. In the Database Engine Configuration window, select "Windows authentication mode" or "Mixed mode" (if you want to use both Windows and SQL Server authentication).
2. If you choose "Mixed mode," enter and confirm the password for the SQL Server system administrator (sa) account.
3. Click "Add Current User" to add your Windows user account as an SQL Server administrator.
4. Click "Next."

#### Step 11: Installation Progress
1. Review your configuration selections and click "Install" to begin the installation process.
2. The installation may take several minutes. Once complete, you will see a message indicating that the installation has succeeded.

#### Step 12: Install SQL Server Management Studio (SSMS)
1. Go to the SSMS download page: 
   `https://aka.ms/ssmsfullsetup`
2. Download the SSMS setup file.
3. Run the downloaded setup file and follow the on-screen instructions to install SSMS.

#### Step 13: Connect to SQL Server
1. Open SQL Server Management Studio (SSMS).
2. In the "Connect to Server" window, select the server name (usually `localhost` or the name of your machine) and the authentication method you set during installation.
3. Click "Connect" to connect to your SQL Server instance.

## Github Usage
- Each person should maintain their own branch. Committing changes directly to the main branch is not permitted!

Sure, here are the steps to create a fork of a repository on GitHub and clone it using Visual Studio:

### Steps to Create a Fork and Clone It Using Visual Studio

#### Step 1: Fork the Repository on GitHub

1. **Log In to GitHub:**
   - Open your web browser and go to [GitHub](https://github.com).
   - Log in to your GitHub account.

2. **Navigate to the Repository:**
   - Find the repository you want to fork by searching for it or navigating directly to the repository URL.

3. **Fork the Repository:**
   - In the top-right corner of the repository page, click the "Fork" button.
   - GitHub will create a copy of the repository under your GitHub account.

#### Step 2: Clone the Forked Repository Using Visual Studio

1. **Open Visual Studio:**
   - Launch Visual Studio on your computer.

2. **Open the GitHub Extension:**
   - If you haven't already, install the GitHub extension for Visual Studio.
   - Go to `Extensions > Manage Extensions` and search for "GitHub Extension for Visual Studio".
   - Install the extension and restart Visual Studio if necessary.

3. **Sign In to GitHub:**
   - Go to `View > GitHub` to open the GitHub pane.
   - Click "Sign in" and log in with your GitHub credentials.

4. **Clone Your Fork:**
   - In Visual Studio, go to `File > Open > Open from Source Control`.
   - Select `GitHub` and then click on the `Clone` button.
   - In the "Clone a repository" window, select your forked repository from the list or enter the repository URL:
     ```plaintext
     https://github.com/Clanatk/NNN/tree/main/AdventureWorks2022
     ```
   - Choose a local path to clone the repository to, then click `Clone`.

