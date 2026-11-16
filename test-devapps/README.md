# DevOps Session - Containerized Django App

A minimal Django web app (modelled on the `python-web-app` example from
[Docker-Zero-to-Hero](https://github.com/iam-veeramalla/Docker-Zero-to-Hero)) that serves a
"Welcome to DevOps Session" page with an image from the Podman Desktop blog post
[Sharing Podman images with a Kubernetes cluster](https://podman-desktop.io/blog/sharing-podman-images-with-kubernetes-cluster).

## Run locally

```bash
python3 -m venv venv1
source venv1/bin/activate
pip install -r requirements.txt
cd devops && python3 manage.py runserver 0.0.0.0:8000
```

Open http://localhost:8000/demo/

## Build and run the container

With podman (or substitute `docker`):

```bash
podman build -t devops-session:latest .
podman run -d -p 8000:8000 devops-session:latest
```

Open http://localhost:8000/demo/
