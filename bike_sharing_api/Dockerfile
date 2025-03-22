FROM python:3.10-slim

WORKDIR /app

# Copy requirements file
COPY requirements.txt .

# Install core dependencies.
RUN apt-get update && apt-get install -y libpq-dev build-essential

# Copy the wheel file into the container
COPY bikeshare_model-0.0.1-py3-none-any.whl .  

# Install dependencies
RUN pip install --no-cache-dir bikeshare_model-0.0.1-py3-none-any.whl -r requirements.txt

# Copy application code
COPY . .

# Expose port for the application
EXPOSE 8001

# Set environment variables
ENV PYTHONPATH=/app

# Command to run the application
CMD ["python", "app/main.py"]