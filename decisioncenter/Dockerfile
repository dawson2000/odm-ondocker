FROM websphere-liberty:webProfile7
ARG ODMDOCKERDIR
LABEL maintainer="ODMDev odmdev_open_source_user@wwpdl.vnet.ibm.com, Laurent GRATEAU <laurent.grateau@fr.ibm.com>"
MAINTAINER ODMDev odmdev_open_source_user@wwpdl.vnet.ibm.com, Laurent GRATEAU <laurent.grateau@fr.ibm.com>
ENV APP_NAME DecisionCenter
ENV ODMDOCKERDIR $ODMDOCKERDIR
RUN mkdir /config/resources
COPY $ODMDOCKERDIR/common/config/decisioncenter /config
COPY $ODMDOCKERDIR/decisioncenter/config /config
COPY $ODMDOCKERDIR/common/config/security /config/resources/security
COPY $ODMDOCKERDIR/dbdriver/derbyclient.jar /config/resources

COPY ./teamserver/lib/commons-logging-1.1.jar /config/lib/
COPY ./teamserver/applicationservers/WLP855/teamserver.war /config/apps/
COPY ./teamserver/applicationservers/WLP855/decisioncenter.war /config/apps/

EXPOSE 9060 9443
