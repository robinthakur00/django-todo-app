# Django Todo App

This repository contains a Django Todo App for managing todo tasks.

## Overview

The Django Todo App provides functionality to create, read, update, and delete tasks.

## Prerequisites

- Python (3.x)
- Django framework
- pip (Python package manager)
- AWS Account
  
## Setup

1. Clone the repository:

    ```bash
    git clone https://github.com/robinthakur00/django-todo-app.git
    ```

2. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

3. Start the Django development server:

    ```bash
    python manage.py runserver
    ```

4. Access the app in a web browser at `http://localhost:8000/`

## File Structure

- `manage.py`: Django management script.
- `todo/`: Main application directory containing models, views, and templates.
- `requirements.txt`: File listing Python dependencies.
- `README.md`: This file, providing project information.

## Usage

- Modify the Django app logic in the `todo/` directory to extend or customize functionality.
- Update HTML templates in the `templates/` directory for UI changes.
- Use additional Django apps or libraries as needed.

## Deploying to AWS with Jenkins Pipeline

Automate deployment using Jenkins Pipeline on AWS:

1. **Set up Jenkins:**
    - Install Jenkins on an AWS EC2 instance.
    - Configure Jenkins with necessary plugins (e.g., Git, AWS).

2. **Create Jenkins Pipeline:**
    - Create a Jenkins job with a Jenkinsfile written in Groovy.
    - Jenkinsfile includes stages for:
        - Fetch the code from Git.
        - Creating a Docker image.
        - Pushing the image to Docker Hub.
        - Deploy the application using Docker Compose

3. **AWS Configuration:**
    - Configure AWS IAM roles for Jenkins to access AWS services.
    - Set up security groups, IAM roles, and permissions for EC2 instances.
    - Configure necessary networking settings to access the application.

4. **Execute Pipeline:**
    - Run the Jenkins Pipeline job to trigger the deployment process.
    - Jenkins Pipeline automates installing dependencies, running Django migrations, and deploying the app on AWS.

## Contributing

Contributions are welcome! Fork the repository, make changes, and submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
