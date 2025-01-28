# Use an official lightweight Python image
FROM python:3.9-alpine  

# Set author label
LABEL Author="NextWork"  

# Set working directory inside the container
WORKDIR /app  

# Install system dependencies and Python requirements in a single step
COPY requirements.txt .  
RUN apk add --no-cache gcc musl-dev libffi-dev && \
    pip3 install --no-cache-dir -r requirements.txt && \
    apk del gcc musl-dev libffi-dev  

# Copy the rest of the application code  
COPY . .  

# Use a non-root user for better security  
RUN adduser -D myuser  
USER myuser  

# Define the command to run the application  
CMD ["python3", "app.py"]
