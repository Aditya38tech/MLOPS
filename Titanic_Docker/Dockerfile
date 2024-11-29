# Step 1: Use a Python base image
FROM python:3.10-slim

# Step 2: Set the working directory inside the container
WORKDIR /app

# Step 3: Install system dependencies and Jupyter Notebook
RUN apt-get update && apt-get install -y \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Step 4: Install Python packages
RUN pip install --no-cache-dir \
    notebook \
    matplotlib \
    pandas \
    numpy \
    seaborn

# Step 5: Copy the images into the container
COPY images/ /app/images/

# Step 6: Expose the Jupyter Notebook default port
EXPOSE 8888

# Step 7: Define the command to start Jupyter Notebook
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
