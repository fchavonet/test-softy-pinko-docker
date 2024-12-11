# Use the latest Ubuntu image as the base.
FROM ubuntu:latest

# Update and install required packages.
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y python3 python3-pip

# Fix for externally managed environments.
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED

# Install Flask using pip3.
RUN pip3 install flask
RUN pip3 install flask flask-cors

# Set the working directory.
WORKDIR /app

# Copy the Flask app into the container.
COPY ./api.py /app/api.py

# Expose the port used by the Flask app.
EXPOSE 5252

# Command to run the Flask app.
CMD ["python3", "api.py"]
