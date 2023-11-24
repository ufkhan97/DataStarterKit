# Use Python 3.11 slim image as the base image
FROM python:3.11-slim

# Set working directory in the Docker container
WORKDIR /app

# Copy the requirements file into the container
COPY requirements.txt .

# Set up a virtual environment
RUN python -m venv /app/venv

# Activate the virtual environment
ENV PATH="/app/venv/bin:$PATH"

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of your application's code into the container
COPY . .

