# 🚀 Streamlit_Evidently

## 🌟 Overview
Streamlit_Evidently is a project that integrates Streamlit with Evidently AI to provide interactive data visualization and monitoring of machine learning models. This setup enables easy model performance tracking and drift detection through a user-friendly interface.

---

## 📂 Project Structure
```bash
📂 Streamlit_Evidently
│── 📂 app/                  # Contains Streamlit app logic
│   ├── 📜 main.py           # Streamlit application entry point
│   ├── 📜 requirements.txt  # Python dependencies
│── 📜 Dockerfile            # Docker configuration file
│── 📖 README.md             # Project documentation
│── 📜 .dockerignore         # Files to ignore in the Docker build
```

---

## 🔧 Prerequisites
Before getting started, ensure you have:
- 🐳 Docker installed
- 🐍 Python (if running locally)
- Required dependencies from `requirements.txt`

---

## 🚀 Installation & Setup
### 1️⃣ Clone the Repository
```bash
git clone https://github.com/AnushkaSharma2024/Streamlit_Evidently.git
cd Streamlit_Evidently
```

### 2️⃣ Build the Docker Image
Docker will create an image based on the `Dockerfile`, setting up the necessary environment.
```bash
docker build -t streamlit-evidently .
```

### 3️⃣ Run the Docker Container
Execute the container and expose it on port 8501.
```bash
docker run -p 8501:8501 streamlit-evidently
```

---

## 🛠️ How It Works
- The `Dockerfile` is based on a lightweight Python image.
- It installs dependencies from `requirements.txt`.
- It copies the Streamlit and Evidently application files.
- When the container starts, it runs `main.py`, launching the Streamlit app with Evidently dashboards.

---

## 🔄 Stopping & Cleaning Up
### Checking Running Containers
To view active Docker containers:
```bash
docker ps
```
To stop a running container:
```bash
docker stop <container_id>
```

### Removing Unused Docker Images
Clean up unnecessary images:
```bash
docker image prune -a
```

---

## 📜 Dockerfile
Below is the content of the `Dockerfile` used in this project:
```Dockerfile
FROM python:3.9-slim

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .

CMD ["streamlit", "run", "main.py", "--server.port=8501", "--server.address=0.0.0.0"]
```

---

## 🙌 Thank You!
Thank you for exploring Streamlit_Evidently! If you have any questions or suggestions, feel free to reach out. 🚀
