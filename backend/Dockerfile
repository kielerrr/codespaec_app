# Base image
FROM mcr.microsoft.com/devcontainers/python:3.10

# Install Node.js (for full stack dev tools, optional)
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y nodejs

# Install Python dependencies
WORKDIR /app
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# Copy app files
COPY . .

# Expose FastAPI port
EXPOSE 8000

# Entrypoint for running directly (can override in compose)
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
