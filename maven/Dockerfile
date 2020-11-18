FROM maven:3.6.3-jdk-8

# change the maven official image source to ali's
RUN rm /usr/share/maven/conf/settings.xml
ADD settings.xml /usr/share/maven/conf/settings.xml
RUN chmod 644 /usr/share/maven/conf/settings.xml

CMD ["mvn"]