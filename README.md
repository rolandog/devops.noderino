# Noderino Fun App! 🚀

A beginner-friendly Node.js server built to help you practice Linux servers, **Environment Variables**, **Docker**, and **CI/CD**! 💚

---

## 🤔 What are Environment Variables?

Before we start, you'll see this project uses **Environment Variables**. 

In software development, you often want your app to behave differently depending on *where* it is running (for example, on your personal laptop vs. a production server) without changing the actual code in `index.js`. 

**Environment variables** are dynamic values stored *outside* of your code that the program reads when it starts up. In Node.js, we access them using `process.env.VARIABLE_NAME`.

### Variables Used in Noderino

If you don't set these variables, the app will automatically fall back to its **Default Value**:

| Variable | What it does | Default Value | Example Custom Value |
| :--- | :--- | :--- | :--- |
| `DESIRED_PATH` | Changes the URL route the server listens to. | `/` | `/secret` |
| `PORT` | Changes the network port the server runs on. | `8080` | `3000` |
| `NUMBER` | A custom number displayed in the greeting message and logs. | `0` | `42` |

---

## 🛠️ Step 1: Clone the Repository

To get a copy of this project onto your computer or Linux server, you need **Git**.

1. Open your terminal.
2. Download (clone) the repository:
   ```bash
   git clone [https://github.com/professordiogodev/devops.noderino.git](https://github.com/professordiogodev/devops.noderino.git)

```

3. Move into the project folder:
```bash
cd devops.noderino

```



---

## 💻 Step 2: Install Node.js & Dependencies

If you are running this on a **Debian or Ubuntu Linux** server, follow these steps to install Node.js and the project packages:

1. **Install Node.js and npm (Node Package Manager):**
```bash
sudo apt update && sudo apt install nodejs -y && sudo apt install npm -y

```


2. **Install the project dependencies** (this downloads `express` and `dotenv` listed in `package.json`):
```bash
npm install

```



---

## ⚙️ Step 3: Set Your Environment Variables

There are **two ways** to give environment variables to your Node app when running it directly on your machine:

### Option A: Using a `.env` file (Recommended)

This project uses a package called `dotenv`, which automatically reads variables from a file named `.env`.

1. Copy the example file included in the project to create your own `.env` file:
```bash
cp .env.example .env

```


2. Open the `.env` file using a terminal text editor like `nano`:
```bash
nano .env

```


3. Edit the values however you like (no spaces around the `=` sign!):
```env
DESIRED_PATH=/fun
PORT=8080
NUMBER=99

```


4. Save and exit (`Ctrl + O`, press `Enter`, then `Ctrl + X` in nano).

### Option B: Passing them directly in the Terminal

You can also set variables temporarily for a single run by typing them right before the `node index.js` command:

```bash
DESIRED_PATH=/hello PORT=3000 NUMBER=7 node index.js

```

---

## ▶️ Step 4: Run and Test the Server!

1. **Start the server:**
```bash
node index.js

```


You will see a message like:
`Server 99 listening on http://localhost:8080/fun`
2. **Test your routes** (open these in your browser, or run `curl` in a second terminal):
* **Your Custom Path (`http://localhost:8080/fun`):**
Displays `<h1>Hello from /fun number 99!</h1>`
* **Healthcheck Route (`http://localhost:8080/healthcheck`):**
Displays `It works!` (Used in DevOps to check if the server is alive!)
* **Any Other Path (`http://localhost:8080/wrong-path`):**
Displays a `404 - Not Found` page.


3. **Stop the server:**
Press `Ctrl + C` in your terminal to shut the server down gracefully.

---

## 🐳 Bonus: Running with Docker

If you have Docker installed, you can run this app inside an isolated container and pass environment variables using the `-e` flag or `--env-file`:

1. **Build the Docker image:**
```bash
docker build -t noderino .

```


2. **Run with custom `-e` flags:**
```bash
docker run -p 8080:8080 -e DESIRED_PATH=/docker -e NUMBER=100 noderino

```


*(Or use your `.env` file directly: `docker run -p 8080:8080 --env-file .env noderino`)*

Have fun! 🚀
