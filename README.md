# 🚀 Machine Learning Model Deployment Using Docker 🐳🤖  

![Docker](https://img.shields.io/badge/Docker-✔️-blue)  
![Python](https://img.shields.io/badge/Python-3.9-blue)  
![Streamlit](https://img.shields.io/badge/Streamlit-✔️-red)  
![AWS EC2](https://img.shields.io/badge/AWS%20EC2-✔️-orange)  
![License](https://img.shields.io/badge/License-MIT-green)  

## 📌 Project Overview  

This project demonstrates how to **containerize an ML model** using **Docker** and deploy it as a **Streamlit web application**. The model is trained on the `mushrooms.csv` dataset and allows users to interact with the predictions in real-time.  

By the end of this tutorial, you'll have a **fully functional ML model** running inside a **Docker container**, ready for **inference or further development**. 🚀  

---

## 🏗️ Features  

✅ **Machine Learning Model** trained on the `mushrooms.csv` dataset  
✅ **Streamlit-based Web App** for interactive user experience  
✅ **Dockerized for Portability** – Run anywhere, independent of system dependencies  
✅ **AWS EC2 Deployment** for **scalability & accessibility**  
✅ **Real-time Predictions & Visualizations**  

---

## 📂 Project Structure  

/ml-docker-app  
│── app.py # Streamlit application with ML model  
│── mushrooms.csv # Dataset used for training  
│── requirements.txt # Python dependencies  
│── Dockerfile # Instructions for building the Docker image  
│── README.md # Project documentation

---

## 🚀 Prerequisites  

Before starting, ensure you have the following installed:  

- **[Docker](https://docs.docker.com/get-docker/)** 🐳  
- **[Python 3.9+](https://www.python.org/downloads/)** 🐍  
- **[Streamlit](https://docs.streamlit.io/)**  
- **AWS EC2 Instance** (for cloud deployment)  

---

## 🔧 Installation & Setup  

### Step 1️⃣: Clone the Repository  

```bash
git clone https://github.com/your-username/ml-docker-app.git
cd ml-docker-app
```
Step 2️⃣: Install Dependencies
```bash
pip install -r requirements.txt
```
Step 3️⃣: Run the App Locally
```bash
streamlit run app.py
```
**🐳 Dockerizing the Application**  

Step 1️⃣: Build the Docker Image
```bash
docker build -t ml-model .
```
Step 2️⃣: Run the Docker Container
```bash
docker run -p 8501:8501 ml-model
```
Step 3️⃣: Access the App
Open your browser and go to:
👉 http://localhost:8501

**🚀 Deploying on AWS EC2 🌐**  

Step 1️⃣: Set Up Your AWS EC2 Instance  

Log in to AWS & navigate to EC2 Dashboard.  

Launch an instance with Amazon Linux 2 AMI.  

Select instance type t2.micro (free tier).  

Configure security groups to allow SSH (port 22) and HTTP (port 8501).  

Launch the instance and download the key pair (.pem file).  


Step 2️⃣: Connect to EC2 via SSH
```bash
ssh -i /path/to/your-key.pem ec2-user@your-ec2-public-ip
```
Step 3️⃣: Install Docker on EC2
```bash
sudo yum update -y
sudo yum install docker -y
sudo service docker start
sudo usermod -a -G docker ec2-user
```
Step 4️⃣: Deploy the Streamlit App
```bash
git clone https://github.com/your-username/ml-docker-app.git
cd ml-docker-app
docker build -t streamlit-app .
docker run -d -p 8501:8501 --name my-streamlit-app streamlit-app
```
Step 5️⃣: Access the App
👉 Open your browser and go to:
http://your-ec2-public-ip:8501

⚡ Automate Deployment (Optional)
Ensure the app runs automatically after system reboot:

```bash
sudo docker update --restart unless-stopped my-streamlit-app
```

**🎉 Conclusion**
Congratulations! 🎉 You have successfully:  


✅ Trained an ML model   

✅ Created an interactive web app with Streamlit  

✅ Containerized the app using Docker  

✅ Deployed the app on AWS EC2  
