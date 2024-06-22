# 🎉 MLflow - Basic Start with ElasticNet Model from Scikit-Learn 🎉

## 🚀 Run Locally
1. Run your application:
    ```bash
    python app.py
    ```
2. Launch the MLflow UI:
    ```bash
    mlflow ui
    ```

## 🌐 Run on DagsHub Server
1. **Create a GitHub Repository** and link it with DagsHub.
2. **Set up the environment** by copying and pasting the following lines into your terminal:
    ```bash
    export MLFLOW_TRACKING_URI=https://dagshub.com/your_username/Project_Name
    export MLFLOW_TRACKING_USERNAME=your_username
    export MLFLOW_TRACKING_PASSWORD=your_password_or_token
    python app.py
    ```

## ☁️ Run on AWS Server

1. **Download and Install AWS CLI:**
    - Create an IAM user with administrator access for this project.
    - Export access and secret keys in AWS CLI by running:
      ```bash
      aws configure
      ```

2. **Set up your AWS environment:**
    - Create an S3 bucket and an EC2 machine (Ubuntu) & add security groups for port 5000.
    - SSH into your EC2 instance and run the following commands:

    ```bash
    sudo apt update
    sudo apt install python3-pip
    sudo pip3 install pipenv
    sudo pip3 install virtualenv
    mkdir mlflow
    cd mlflow
    pipenv install mlflow
    pipenv install awscli
    pipenv install boto3
    pipenv shell
    ```

3. **Configure AWS credentials:**
    ```bash
    aws configure
    ```

4. **Run the MLflow server and connect to the S3 bucket:**
    ```bash
    mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-bucket
    ```

5. **Update the Tracking URI:**
    ```bash
    export MLFLOW_TRACKING_URI=http://ec2-xx-xxx-xx-xxx.compute-1.amazonaws.com:5000
    ```

