FROM jboss/keycloak:latest

ADD enableProxy.xsl /opt/jboss/keycloak/

RUN \
	java -jar /usr/share/java/saxon.jar \
	-s:/opt/jboss/keycloak/standalone/configuration/standalone.xml \
	-xsl:/opt/jboss/keycloak/enableProxy.xsl \
	-o:/opt/jboss/keycloak/standalone/configuration/standalone.xml; \
	java -jar /usr/share/java/saxon.jar \
	-s:/opt/jboss/keycloak/standalone/configuration/standalone-ha.xml \
	-xsl:/opt/jboss/keycloak/enableProxy.xsl \
	-o:/opt/jboss/keycloak/standalone/configuration/standalone-ha.xml; \
	rm /opt/jboss/keycloak/enableProxy.xsl
