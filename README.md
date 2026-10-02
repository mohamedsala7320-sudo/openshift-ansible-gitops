# 🚀 Microservices Deployment on OpenShift via Ansible & GitHub Actions (GitOps)

A professional DevOps portfolio project demonstrating automated CI/CD pipelines, Infrastructure as Code (IaC) with Ansible, containerized microservices (Flask backend & Nginx frontend), and deployment on Red Hat OpenShift.

---

## 🛠️️ Architecture & Tech Stack

* **Frontend:** Nginx serving static assets and proxying requests.
* **Backend:** Python Flask REST API.
* **Containerization:** Docker & DockerHub (`mosala7320/frontend`, `mosala7320/backend`).
* **CI/CD Pipeline:** GitHub Actions (Automated build & push on every commit).
* **Automation / IaC:** Ansible Playbooks for OpenShift orchestration.
* **Target Platform:** Red Hat OpenShift.

---

## 🔄 CI/CD Pipeline Workflow

The project utilizes GitHub Actions for continuous integration and delivery:
1. **Trigger:** Code pushes to the `main` branch.
2. **Build:** Compiles Docker images for both Flask backend and Nginx frontend.
3. **Authentication:** Securely logs in to DockerHub using encrypted GitHub Secrets (`DOCKER_USERNAME` and `DOCKER_PASSWORD`).
4. **Push:** Automatically publishes the latest production-ready images to DockerHub.

---

## 📂 Project Structure

```text
openshift-ansible-gitops/
├── .github/
│   └── workflows/
│       └── ci-cd.yml       # GitHub Actions automated pipeline
├── ansible/
│   └── playbooks/
│       └── deploy.yaml     # Ansible automation for OpenShift
├── src/
│   ├── backend/            # Flask REST API source & Dockerfile
│   └── frontend/           # Nginx frontend source & Dockerfile
└── README.md

```


---

## 🧪 Local Testing & Verification

To verify the microservices locally using Docker:

1. **Run the Backend (Flask API):**
   ```bash
   docker run -d -p 5000:5000 mosala7320/backend:latest
   ```

   Test the backend endpoint
   ```bash
   curl http://localhost:5000
   ```

2. **Run the Frontend (Nginx):**
   ```bash
   docker run -d -p 8080:80 mosala7320/frontend:latest
   ```
 
   "Open your browser at http://localhost:8080 
    👉 to view the application interface."

---

## ⚙️  Deployment on OpenShift via Ansible

To orchestrate and deploy the microservices cluster using the automated Ansible playbook:
    
     ```bash
     ansible-playbook ansible/playbooks/deploy.yaml
     ```
---

👨‍💻 Author

Mohamed Salah — DevOps & Cloud Engineer








