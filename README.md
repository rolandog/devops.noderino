# Noderino Fun App! 🚀

A small Node.js server designed to help you practice CI/CD, environment variables, and containerization! 💚

---

## 🛠️ Prerequisites

Before you begin, make sure you have **Git** installed on your computer to download the code.

*   Check if Git is installed:
    ```bash
    git --version
    ```

---

## 📦 Step 1: Clone the Repository

To get a copy of the project on your local machine or server, open your terminal and run:

```bash
git clone https://github.com/professordiogodev/devops.noderino.git

```

Then, move into the project directory:

```bash
cd devops.noderino

```

---

## ⚙️ Step 2: Configure Environment Variables (Optional)

This app uses environment variables to customize its behavior.

1. Look for the `.env.example` file in the project folder.
2. Create a copy of it and name the new file `.env`:
```bash
cp .env.example .env

```


3. Open the `.env` file in any text editor and customize the variables:

| Variable | Description | Default / Example |
| --- | --- | --- |
| `DESIRED_PATH` | Changes the URL path that the server listens to. | `/` or `/noderino` |
| `PORT` | Changes the port that the server listens on. | `8080` |
| `NUMBER` | An arbitrary number displayed by the server. | `42` |

---

## 💻 Step 3: Run Locally (Debian / Ubuntu Linux)

If you are running this app directly on a Linux server (like Ubuntu or Debian), follow these steps:

### 1. Install Node.js and npm

Update your package list and install Node.js and npm:

```bash
sudo apt update && sudo apt install nodejs -y && sudo apt install npm -y

```

### 2. Install Dependencies

Install the required project packages:

```bash
npm install

```

### 3. Run the Server

Start the application:

```bash
node index.js

```

You should see a message in your terminal saying the server is running! 🎉

---

## 🐳 Step 4: Run with Docker (Alternative)

If you want to practice containerization, you can run the app using Docker:

1. Build the Docker image:
```bash
docker build -t noderino-app .

```


2. Run the Docker container (mapping port 8080):
```bash
docker run -p 8080:8080 noderino-app

```



---

Have fun learning and exploring DevOps! 🚀
