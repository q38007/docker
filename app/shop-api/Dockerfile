#Base image
FROM tnt/python

#Maintainer
MAINTAINER x.j

# Add www user
RUN useradd -s /sbin/nologin -M www

# ADD file
ADD app.py /opt/app.py
ADD requirements.txt /opt/
ADD supervisord.conf /etc/supervisord.conf
ADD app-supervisor.ini /etc/supervisord.d/

# pip
RUN /usr/bin/pip2.7 install -r /opt/requirements.txt

# Port
EXPOSE 22 5000

#CMD
CMD ["/usr/bin/supervisord", "-c", "/etc/supervisord.conf"]
