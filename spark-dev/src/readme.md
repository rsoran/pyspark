# ⚡ PySpark Development Environment (VS Code Dev Container)

This repository contains a reproducible, single-node **PySpark** development environment pre-configured using **VS Code Dev Containers**. It includes the necessary **Python**, **PySpark 3.5.0**, and **Java 17** components, ready for immediate data processing.

---

## 🚀 Getting Started

### Prerequisites

1.  **Docker Desktop** (or equivalent Docker engine)
2.  **Visual Studio Code**
3.  **VS Code Dev Containers Extension**   --this is a must

### Setup in VS Code

1.  **Clone the Repository:** Clone this repo to your local machine.
2.  **Rename the devcontainer to .devcontainer this is a very important step**
3.  **Open Folder:** Open the main project folder (`/spark-dev` or similar) in VS Code.
4.  **Reopen in Container:** VS Code should automatically detect the `.devcontainer` folder and prompt you to **"Reopen in Container."** Click this button.
    * *If the prompt does not appear:* Open the Command Palette (`Ctrl+Shift+P` or `F1`) and run **`Dev Containers: Rebuild and Reopen in Container`**.
5.  **Wait:** VS Code will build the Docker image (this may take a few minutes the first time) and connect your workspace to the container.

---

## ✅ Verification

Once connected, open the terminal in VS Code (`Ctrl+\``) and confirm the setup:

### 1. PySpark Shell

Run the PySpark shell:

```bash
pyspark

# You should see the Spark Welcome screen. Type 'exit()' to quit.
