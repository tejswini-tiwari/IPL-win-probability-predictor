# Base image
FROM python:3.10

# Working directory
WORKDIR /app

# Copy files
COPY requirements.txt
# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt
COPY . .

# Expose port
EXPOSE 8000

# Start API
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]