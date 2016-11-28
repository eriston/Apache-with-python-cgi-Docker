# Dockerfile for Apache with python cgi

A dockerfile to create an image for an Apache server with python cgi enabled, based on the most recent Ubuntu LTS 16.04.


To build (from within the same directory as the Dockerfile):
 - sudo docker build --no-cache=false -t site_name .


To run:
- sudo docker run -d -p 8080:80 -v '/path/to/logs':/var/log/apache2 -v '/path/to/site/files':/var/www/html image_name

- 8080 is the exposed external port



The following lines are specific to the existing code the container was developed to run and not a requirement of the python cgi:

RUN apt-get -y install python-pil python-matplotlib python-scipy python-sklearn

RUN ln -sf /usr/bin/python /usr/local/bin/python
