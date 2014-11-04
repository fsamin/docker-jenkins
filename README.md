docker-jenkins
==============

##Dockerfile
<pre>
  FROM fsamin/docker-oracle-java7
  MAINTAINER François Samin francois.samin@gmail.com
  ADD http://mirrors.jenkins-ci.org/war/latest/jenkins.war /opt/jenkins.war 
  RUN ln -sf /jenkins /root/.jenkins
  ENTRYPOINT [“java”, “-jar”, “/opt/jenkins.war”] 
  EXPOSE 8080 VOLUME [“/jenkins”] 
  CMD [“”]
</pre>
##Start the container
<pre>
  docker run -d -p 8080:8080 –privileged -t -v /data/jenkins:/jenkins fsamin/docker-jenkins
</pre>
