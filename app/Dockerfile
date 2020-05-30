# Use an official Python runtime as a parent image
FROM python:2.7-slim

COPY 95proxies /etc/apt/apt.conf.d/

ENV http_proxy http://172.17.0.1:3128/
ENV https_proxy http://172.17.0.1:3128/

# ENV http_proxy http://127.0.0.1:3128/
# ENV https_proxy http://127.0.0.1:3128/

# RUN apt install net-tools
# RUN ifconfig
# Debug
RUN echo http proxy: $http_proxy $HTTP_PROXY
RUN echo https proxy: $https_proxy $HTTPS_PROXY

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Make port 80 available to the world outside this container
EXPOSE 80

# Define environment variable
ENV NAME World

# Run app.py when the container launches
CMD ["python", "app.py"]
