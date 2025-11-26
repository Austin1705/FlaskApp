# 1. Use an official Python runtime as the base image for the container
FROM python:3.11-slim

# 2. Set the working directory inside the container to /app
# All subsequent instructions (COPY, RUN, etc.) will be executed relative to this path
WORKDIR /app

# 3. Copy the requirements file into the container
# This is done first so the RUN command can leverage Docker's build cache
COPY requirements.txt .

# 4. Install Flask and all dependencies listed in requirements.txt
# This fulfills the "Installing Flask dependencies" requirement 
RUN pip install --no-cache-dir -r requirements.txt

# 5. Copy the rest of the application code (app.py, test_app.py, etc.) into the container
# This fulfills the "Copying the code into the container" requirement 
COPY . .

# 6. Inform Docker that the container listens on the specified port 5000
# This fulfills the "Specifying the port" requirement 
EXPOSE 5000

# 7. Define the command to run the application when the container starts
# This fulfills the "Running the Flask application" requirement 
CMD ["python", "app.py"]