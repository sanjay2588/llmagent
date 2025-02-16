
# AI Proxy Agent Project

This project implements an AI proxy agent system. Follow the instructions below to set up and run the project.

## Prerequisites

- Python 3.8+
- uv (Python package installer)
- Podman/Docker
- Git Bash (Windows) or Terminal (Unix-based systems)

## Setup Instructions

### 1. Environment Configuration

First, set up your AI Proxy token. You can do this in two ways:

#### Option A: Using .env file
Create a `.env` file in the project root:
```bash
AIPROXY_TOKEN=your_token_here
```

#### Option B: Using environment variables

For Bash/Git Bash:
```bash
export AIPROXY_TOKEN=your_token_here
```

For PowerShell:
```powershell
$env:AIPROXY_TOKEN="your_token_here"
```

### 2. Configuration Updates

Update the email address in `tasksA.py` to your email address:
```python
email = "your.email@example.com"  # Replace with your email
```

### 3. Running the Application

Open two terminal windows:

Terminal 1:
```bash
uv run app.py
```

Terminal 2:
```bash
uv run evaluate.py
```

## Docker/Podman Deployment

### Building the Image

```bash
podman build -t llmagent2 .
podman images  # Note down the image ID
```

### Running the Container

```bash
podman run <image_id>
```

### Publishing to Docker Hub

1. Create a new repository on Docker Hub
2. Tag your image:
```bash
podman tag <image_id> username/repository_name:tag_name
```

3. Login to Docker Hub:
```bash
podman login docker.io
```

4. Push the image:
```bash
podman push docker.io/username/repository_name:tag_name
```

## Project Structure

```

├── app.py              # Main application file
├── tasksA.py          # Task definitions
├── evaluate.py        # Evaluation script
├── datagen.py        # Data generation utilities
├── Dockerfile        # Container configuration
└── .env              # Environment variables (create this)
```

## Notes

- Ensure all dependencies are installed before running the application
- Keep your AI Proxy token secure and never commit it to version control
- Make sure ports specified in the application are available before running

## Troubleshooting

If you encounter any issues:
1. Verify your AI Proxy token is correctly set
2. Ensure all required ports are available
3. Check your email configuration in tasksA.py
4. Verify all dependencies are installed correctly

