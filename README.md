# 🚀 FastAPI K8s Demo

This is a simple production-style example that demonstrates how to run a **FastAPI** application backed by **PostgreSQL**, deployed on **Kubernetes** using **Minikube**. It includes support for:

* Dockerized FastAPI app
* PostgreSQL with persistent volume
* Kubernetes manifests (Deployment, Service, Ingress)
* **Secrets** for DB credentials
* **ConfigMaps** for configuration values
* Minikube **Ingress** with custom domain routing
* Optional support for **live reload** and persistent storage

---

## 🧱 Features

* ✅ FastAPI app with PostgreSQL backend
* ✅ Minikube setup with Ingress routing
* ✅ Configurations via `Secrets` and `ConfigMaps`
* ✅ Persistent volume for PostgreSQL data
* ✅ Kubernetes-native deployment
* ✅ Easy local testing with domain mapping

---

## 📦 Stack

* **FastAPI** – Python web framework
* **PostgreSQL** – Relational database
* **Docker** – Containerization
* **Kubernetes (Minikube)** – Local K8s environment
* **Ingress** – Route traffic to FastAPI service
* **Secrets & ConfigMaps** – Manage configuration and credentials

---

## 🚦 Setup Instructions

1. **Start Minikube with Ingress:**

   ```bash
   minikube start --addons=ingress
   ```

2. **Enable Docker environment in Minikube:**

   ```bash
   eval $(minikube docker-env)
   ```

3. **Build the FastAPI Docker image:**

   ```bash
   docker build -t fastapi-demo .
   ```

4. **Apply all Kubernetes resources:**

   ```bash
   kubectl apply -f k8s/
   ```

5. **Update `/etc/hosts` to enable domain routing:**

   ```bash
   echo "$(minikube ip) fastapi.local" | sudo tee -a /etc/hosts
   ```

6. **Access the application:**

   * Home: [http://fastapi.local](http://fastapi.local)
   * DB Check: [http://fastapi.local/db-check](http://fastapi.local/db-check)

---

## 📁 Kubernetes Resources

* **`deployment.yaml`** – FastAPI deployment
* **`postgres-deployment.yaml`** – PostgreSQL deployment + volume
* **`service.yaml`** – Exposes FastAPI service internally
* **`postgres-service.yaml`** – PostgreSQL ClusterIP service
* **`ingress.yaml`** – Ingress rule for FastAPI routing
* **`secret.yaml`** – Database credentials
* **`configmap.yaml`** – Database name and configs

---

## 🛠️ Customization

You can extend this project to include:

* ✅ pgAdmin or pgvector
* ✅ Init SQL scripts using Kubernetes `initContainers`
* ✅ Helm chart packaging
* ✅ CI/CD pipeline integration (GitHub Actions, etc.)

---

## 📜 License

This project is open-source and free to use under the [MIT License](LICENSE).
