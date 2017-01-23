With this project, you can easily deploy the **latest** JFrog Artifactory to your OpenShift Online account.

#Forked
This repository was forked from **https://github.com/andershedstrom/openshift-community-artifactory**, which was configured for *v4.4.0*. 

**It was then modified so that it always (dynamically) uses the latest version.**

The installlation uses the following link to fetch the latest version: https://api.bintray.com/content/jfrog/artifactory/jfrog-artifactory-oss-%24latest.zip;bt_package=jfrog-artifactory-oss-zip

#How to Deploy
using `Openshift 2` command line tool (`rhc`), and type the following command to deploy:

    rhc create-app artifactory \
    https://cartreflect-claytondev.rhcloud.com/reflect?github=alexbt/openshift-artifactory-latest \
    https://cartreflect-claytondev.rhcloud.com/reflect?github=alexbt/openshift-community-oracle-jdk-8
    
The process *may* take some time (accessing the url will display a *503*), if that is the case and you are wondering, you may connect to the server and tail 
the logs:

    ssh 588fef487628e10cd10000f0@$APPNAME-$USER.rhcloud.com
    tail -f $OPENSHIFT_PRIMARY_CARTRIDGE_DIR\jfrog-artifactory\logs\artifactory.log
