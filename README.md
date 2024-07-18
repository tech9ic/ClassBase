# 🎓 ClassBase 📚

Welcome to **ClassBase** - your ultimate school management solution designed to streamline administrative tasks and enhance communication within educational institutions. This application empowers teachers, students, and administrators alike to manage their roles efficiently and effectively.

## Features 🚀

### Teacher 👩‍🏫👨‍🏫
- **Account Approval**: Teachers apply for jobs and get their accounts approved by the admin before accessing their dashboard.
- **Attendance Management**: Teachers can take attendance for classes and view attendance records later.
- **Notice Board**: Teachers can publish notices to students, such as assignment submission deadlines.

### Student 📝🎒
- **Admission and Approval**: Students sign up for accounts and await admin approval to access their dashboard.
- **View Attendance**: Students can view their attendance records but cannot access others' attendance.
- **Notice Viewing**: Students can view announcements but cannot post them.

### Admin 👑
- **Role and Responsibility**: Admins manage job/admission requests, approving or rejecting them as needed.
- **Data Management**: Admins update student and teacher details as required.
- **Notice Management**: Admins can post announcements for all users.

## Installation 🛠️

To run this project locally:

1. Install Python 3.7.6 (Ensure "Add to Path" is checked during installation).
2. Open Terminal and navigate to the project directory.
3. Install dependencies:
`python -m pip install -r requirements.txt`
4. Perform database migrations:
```
py manage.py makemigrations
py manage.py migrate
```
5. Start the development server:
`py manage.py runserver`
6. Open your web browser and enter the following URL: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

## Setup for Contact Us Page 📧

To configure the "Contact Us" page:

1. In `settings.py`, update the following settings with your email credentials:

```text
EMAIL_HOST_USER = 'youremail@gmail.com'
EMAIL_HOST_PASSWORD = 'your email password'
EMAIL_RECEIVING_USER = 'youremail@gmail.com'
```
2. Log in to your Gmail account and enable access for less secure apps using this link.

## Disclaimer ℹ️
ClassBase is developed for demonstration purposes only and is not intended for use in real-world applications.

# How to Run the App Using Docker 🐳

## Prerequisites:

Before starting, ensure you have the following:
- Docker installed: Ensure you have Docker Desktop or the command-line Docker engine installed on your system. You can download it from the official website: [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- Basic Docker knowledge: Familiarity with Docker concepts like images, containers, and Dockerfiles will be helpful.

## Steps

### Create a Dockerfile

1. **Create Dockerfile**:
   - In the root directory of your project, create a new file named `Dockerfile` (case-sensitive).

2. **Paste the following content into the Dockerfile**:
   ```
   # Use a base image appropriate for your project's language (e.g., python:3.9-slim)
   FROM python:3.9-slim

   # Set the working directory within the container
   WORKDIR /app

   # Copy requirements.txt and install dependencies
   COPY requirements.txt ./
   RUN pip install -r requirements.txt

   # Copy your project code
   COPY . .

   # Expose the port used by your project (adjust as needed)
   EXPOSE 8000

   # Specify the command to run when the container starts (replace with your actual command)
   CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]


### Build the Docker Image:

- Open a terminal or command prompt and navigate to your project's root directory.

Run the following command to build the Docker image, replacing my-project-name with the desired name for your image:

```Bash
docker build -t my-project-name .
```

**Run the Docker Container:**

Run the following command to start a container based on the built image:

```Bash
docker run -d -p 8000:8000 my-project-name
```

<br>
> Made with ❤️ by tech9ic
