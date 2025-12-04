FROM python:3.11

WORKDIR /backend

# Install system dependencies
RUN apt-get update && apt-get install -y build-essential curl && rm -rf /var/lib/apt/lists/*

# Install uv
RUN pip install uv

# Copy pyproject.toml first
COPY pyproject.toml .

# Install dependencies
RUN uv pip install --system -e .

# Copy backend code
COPY . .

EXPOSE 8000

# Run FastAPI
CMD ["python", "-m", "uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
