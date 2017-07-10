FROM registry.access.redhat.com/openshift3/jenkins-1-rhel7:1.609-15

ADD config-cloud.xml credentials.xml /opt/openshift/

# Install additional plugins and modify files
RUN mkdir -p /opt/openshift/plugins && \
          cat /opt/openshift/credentials.xml > /opt/openshift/configuration/credentials.xml && \
          curl -sSL -f https://updates.jenkins-ci.org/download/plugins/swarm/2.0/swarm.hpi -o /opt/openshift/plugins/swarm.jpi && \
		  touch /opt/openshift/plugins/credentials.jpi.pinned && \
		  chmod -R og+rw /opt/openshift/plugins && \
		  rm -rf /opt/openshift/config-cloud.xml /opt/openshift/credentials.xml
