# DataStarterKit

This is a guide to getting any computer running the same environment for data science needs. It'll use docker to create the same environment. That environment will include python and essential tooling like Jupyter, Pandas, NumPy, etc. 

The commands below are for your terminal. 

**Contents:**
1. Install Docker
2. Set Up Container 


**Recommended:**
- Use VSCode with the following extensions:
  - Python
  - Jupyter
  - Remote Explorer (common if setting up over SSH and allows you to access the container just like your local environment to explore files, edit in a notebook, and run commands in terminal)


## Install Docker 

### Step 1: Update and Install Dependencies. Run:

```
sudo apt-get update
sudo apt-get upgrade
```

Then, install the necessary packages for Docker:

```
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```
### Step 2: Add Docker’s GPG Key
This key ensures the integrity of the software you're installing:

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
### Step 3: Set Up the Stable Repository
Instead of adding the repository directly, let's add it in a way that specifies the architecture and ensures we're accessing the stable version:

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

### Step 4: Update the apt Package Index
```
sudo apt-get update
```
### Step 5: Install Docker CE
```
sudo apt-get install docker-ce
```
### Step 6: Test the Docker Installation
Run the hello-world Docker image to confirm Docker is correctly installed and functioning:
```
sudo docker run hello-world
```

## Pull Starter Image 
### Step 7: Pull the Base Image
This image installs python 3.11 as well as useful libraries for data analysis and vizualisation such as streamlit, plotly, ipykernel(for jupyter), and psycopg2(for postgresSQL connections).
```
sudo docker pull ufkhan97/datastarter
```

### Step 8: Build the Image
```
sudo docker build -t datastarter .
```

### Step 9: Run the Image
```
sudo docker run -it --name datastarter datastarter
```

### Step 10: Verify 
The -it flag in step 9 will launch an interactive terminal when the container runs. If this succeeds then your installation is succesful. 
