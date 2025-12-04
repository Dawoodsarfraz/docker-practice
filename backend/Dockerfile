# Use Python 3.11 base image
FROM python:3.11-slim

# Set working directory
WORKDIR /backend

# Copy pyproject.toml and install dependencies using uv
COPY pyproject.toml . 
RUN uv sync

# Copy the rest of the application code
COPY . .

# Expose FastAPI port
EXPOSE 8000

# Run FastAPI using uvicorn
CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]
