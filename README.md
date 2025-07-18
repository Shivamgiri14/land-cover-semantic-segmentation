<div align="center">
 


</div>

----
 


---

## 🚀 Getting Started <a name="getting-started"></a>

### ✅ Prerequisites <a name="prerequisites"></a>
 
 - <b>Dataset prerequisite for training</b>:
 
 Before starting to train a model, make sure to download the dataset from <a href="https://landcover.ai.linuxpolska.com/" target="_blank">LandCover.ai</a> or from <a href="https://www.kaggle.com/datasets/adrianboguszewski/landcoverai" target="_blank">kaggle/LandCover.ai</a>, and copy/move over the downloaded directories 'images' and 'masks' to the 'train' directory of the project.

### 🐳 Setting up and Running the project with Docker <a name="with-docker"></a>
 
 First and foremost, make sure that <a href="https://www.docker.com/">Docker</a> is installed and working properly in the system.
 
 > 💡 Check the **Dockerfile** added in the repository. According the instructions provided in the file, comment and uncomment the mentioned lines to setup the docker image and container either to **train** or **test** the model at a time.
 
 1. Clone the repository:
 ```shell
 git clone https://github.com/Shivamgiri14/land-cover-semantic-segmentation.git
 ```
 2. Change to the project directory:
 ```shell
 cd land-cover-semantic-segmentation
 ```
 3. Build the image from the Dockerfile:
 ```shell
 docker build -t segment_project_image .
 ```
 4. Running the docker image in a docker container:
 ```shell
 docker run --name segment_container -d segment_project_image
 ```
 5. Copying the output files from the container directory to local project directory after execution is complete:
 ```shell
 docker cp segment_container:/segment_project/models ./models
 docker cp segment_container:/segment_project/logs ./logs
 docker cp segment_container:/segment_project/output ./output
 ```
 6. Tidying up:
 ```shell
 docker stop segment_container
 docker rm segment_container
 docker rmi segment_project_image
 ```
 
 If <a href="https://www.docker.com/">Docker</a> is not installed in the system, follow the below methods to set up and run the project without Docker.

### 💻 Setup (Without 🐳 Docker) <a name="setup"></a>
 
 1. Clone the repository:
 ```shell
 git clone https://github.com/Shivamgiri14/land-cover-semantic-segmentation.git
 ```
 2. Change to the project directory:
 ```shell
 cd land-cover-semantic-segmentation
 ```
 3. Setting up programming environment to run the project:
 
 - If using an installed <a hre="https://docs.conda.io/en/latest/">conda</a> package manager, i.e. either Anaconda or Miniconda, create the conda environment following the steps mentioned below:
 ```shell
 conda create --name <environment-name> python=3.9
 conda activate <environment-name>
 ```
 - If using a directly installed python software, create the virtual environment following the steps mentioned below:
 ```shell
 python -m venv <environment-name>
 <environment-name>\Scripts\activate
 ```
 4. Install the dependencies:
 ```shell
 pip install -r requirements.txt
 ```

### 🤖 Running the project (Without 🐳 Docker) <a name="running-the-project"></a>
 
 Running the model training and testing/inferencing scripts from the project directory. It is not necessary to train the model first mandatorily, as a simple trained model has been provided to run the test and check outputs before trying to fine-tune the model.
 
 1. Run the model training script:
 ```shell
 cd src
 python train.py
 ```
 2. Run the model test (with images and masks) script:
 ```shell
 cd src
 python test.py
 ```
 3. Run the model inference (with images only, masks not required) script:
 ```shell
 cd src
 python inference.py
 ```

----

## 📝 Citing <a name="citing"></a>
```
@misc{
  Author = {Shivam Kumar Giri},
  Title = {Land Cover Semantic Segmentation PyTorch},
  Year = {2025},
  Publisher = {GitHub},
  Journal = {GitHub repository},
  
}
```

----



<p align="right">
 <a href="#top"><b>🔝 Return </b></a>
</p>

---
