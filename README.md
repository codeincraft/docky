# docky
An end-to-end AI-powered medical chatbot designed to provide preliminary health guidance, symptom analysis, and conversational support using modern Machine Learning and NLP techniques. The project demonstrates how to move from experimentation in notebooks to a production-ready, deployable AI system.

# How to Run
### Steps

Clone the repository

```bash
project repo: https://github.com
```

### Step 1 create a conda environment after opening the repository

```bash
conda create -n docky python=3.10 -y
...

```bash
conda activate docky
```

### Step 2 - install the requirements
```bash
pip install -r requirements.txt

```

### Create a .env file in the root directory and add your Pinecone & openai credentials as follows:
```bash
PINECONE_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
OPENAI_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

# run the following command to store embeddings to pinecone
python store_index.py

# Finally run the following command
python app.py

### Now
open up localhost:

### Techstack Used:

```bash
Python
LangChain
Flask
GPT
Pinecone
```

### AWS-CICD-Deployment-with-Github-Actions
```bash
1. Login to AWS console.
2. Create IAM user for deployment
```

#with specific access

1. EC2 access : It is virtual machine

2. ECR: Elastic Container registry to save your docker image in aws


#Description: About the deployment

1. Build docker image of the source code

2. Push your docker image to ECR

3. Launch Your EC2 

4. Pull Your image from ECR in EC2

5. Lauch your docker image in EC2

#Policy:

1. AmazonEC2ContainerRegistryFullAccess

2. AmazonEC2FullAccess

```bash
3. Create ECR repo to store/save docker image
```
- Save the URI: 970547337635.dkr.ecr.ap-south-1.amazonaws.com/medicalchatbot

```bash
4. Create EC2 machine (Ubuntu)
```
```bash
5. Open EC2 and Install docker in EC2 Machine:
```
#optinal

sudo apt-get update -y

sudo apt-get upgrade

#required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker


```bash
6. Configure EC2 as self-hosted runner:
```
setting>actions>runner>new self hosted runner> choose os> then run command one by one

```bash
7. Setup github secrets:
```
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
ECR_REPO
PINECONE_API_KEY
OPENAI_API_KEY