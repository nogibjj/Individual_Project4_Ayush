# Individual Project #4: Auto Scaling Flask App Using Any Platform As a Service

## INTRODUCTION
Following are the major features of this project - 
1. Hugging Face LLM Transformers model is used to develop a Text Summariazation model within Flask.
2. The functioning container was hosted on Docker Hub.
3. Azure web app was used to successfully deploy the container to a public endpoint directly through Docker.
4. Using Azure services for Auto Scaling Flask App.

## FLASK APP
The flask app is a simple text summarization application that is aimed at giving a user a summary of the text that he inputs. It makes use of the huggingface text-summarization model for the same. 

The link : https://textsummarizationapp.azurewebsites.net/

The following images represent the functioning of the text summarization app. 

![ Text Summarization Window](https://github.com/nogibjj/Individual_Project4_Ayush/blob/main/Images/Text_Summarization_image.png)

![ Text Summarization Result](https://github.com/nogibjj/Individual_Project4_Ayush/blob/main/Images/Text_Summarization_result.png)

## HTML files 
The two html files: index.html and output.html are the scripts that dictate how the user interface will work for the flask app. These are extremely simple examples of HTML files, with only a text insert box, button, and text display. For any future projects, these could be further developed to make it more interactive. 

## CI/CD Pipeline:
This project also has a CI/CD pipeline, which is successfully running and consists of the following steps:

1. Setting up a Python environment
2. Installing project dependencies and packages
3. Formatting using Black formatter
4. Linting used Ruff

### Creating the Flask App
1. Create HTML files that contains the basic skeleton of how the user will interact with the web browser.
2. Create a flask app that runs your python code. The code is available in app.py in this repository.
3. The python file needs to be connected with the HTML files.
4. Run the app locally to make sure everything is working as expected. You can do so by running python app.py in your terminal.

##### Libraries to be installed 
You can find the list of libraries in the requirements.txt file. You can install them by running pip install -r requirements.txt in your terminal. Some of the unique ones required specifically for this project were:

1. Flask
2. Transformers
3. tensorflow
4. Torch

### Creating a DockerHub repository , App Deployment & Autoscaling : 

1. Create a DockerHub repository.
2. Create a Microsoft Azure Web App (My Web Application name is TextSummarizationApp)
3. While choosing how to publish your code, we have used 'Docker Container' to deploy the app as a Docker Image.
4. Install DockerHub application and login.
5. Create a Dockerfile in the main project directory.
This will install use Python 3.10.8 as the base image, set the working directory to /app and copy the local directory contents into the container, install required Python packages from a requirements.txt file, expose port 5000 to allow external access, set an environment variable NAME to myenv, and execute a Flask application (flask_app.py) with specified host and port configurations when the container starts.
6. Then, you can build your dockerimage using the command: ```docker build -t <YOUR_DOCKER_USERNAME>/<YOUR_IMAGE_NAME>```
I have two Dockerfiles because these two Dockerfiles serve different purposes - one for deploying the Flask application in a production-like environment, and the other for setting up a development environment. The Dockerfile is located in the main project directory and is used for deploying your Flask application. It includes instructions to set up a Python environment, copy your project files, install dependencies, and run your Flask app. The Dockerfile located in the .devcontainer folder is typically used in development environments, especially when working with Visual Studio Code or VS Code's Remote - Containers extension.

7. Perform the following operations to push the docker image and run it. 
   ```docker push <YOUR_USERNAME>/<YOUR_IMAGE_NAME>```
   ```docker run -p 5000:5000 <YOUR_IMAGE_NAME>```

8. Configure Azure web App with Dockerhub
9. Configure the Auto Scaling feature. 
10. Once configured, the app is deployed and can be run and tested. 







   







