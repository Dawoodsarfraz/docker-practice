FROM python:3.11-slim

WORKDIR /frontend

# Install system dependencies
RUN apt-get update && apt-get install -y build-essential curl && rm -rf /var/lib/apt/lists/*

# Install Python packages globally
COPY pyproject.toml .
RUN pip install --upgrade pip uv streamlit watchdog

# Copy the rest of your code
COPY . .

EXPOSE 8501

# Run Streamlit
CMD ["streamlit", "run", "main.py", "--server.port=8501", "--server.address=0.0.0.0"]
