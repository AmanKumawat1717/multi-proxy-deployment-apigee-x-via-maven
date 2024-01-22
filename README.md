# multi-proxy-deployment-apigee-x-via-maven
Getting Started
Sign up for an Apigee Account!. Not required if already provided.
Download and install Maven 3.*
Clone this repo https://github.com/apigee/apigee-deploy-maven-plugin
Execute mvn clean install -Ptest -Denv=${env_name} -Dorg=${Org} -Dbearer=${Token} -Dproxyname=${proxyName}

That's it! If everything ran smooth, you will see BUILD SUCCESS message at the of the execution of this command. Next steps, learn a bit of Maven to customize the pom.xml.

Basic Commands – apigee.options
Configure, package, import, deploy, and test bundle (default validate apigee.option) – Creates new revision
mvn clean install -Ptest -Denv=${env_name} -Dorg=${Org} -Dbearer=${Token} -Dproxyname=${proxyName}

The following are available options:
a. clean - This will delete the last deployed revision in an environment.

b. validate - This will validate a bundle before importing. Thus if you want strict validation then its required.

c. inactive - This will just import the bundle without activating the bundle.

d. override - This is used for seamless deployment. This must be supplied with apigee.override.delay parameter. The apigee.override.delay expects delay to be given in seconds.

e. update - It will update the deployed revision . This is similar to import with validation but no new revision is created. If there any errors in the bundle, error is thrown and the existing bundle is left intact. In case the revision they are trying to update is deployed, it will internally trigger undeployment and deployment. It is completely in the background and not visible in the response. It is advised not to update the deployed revision. (UI could show a warning or something in this case).
