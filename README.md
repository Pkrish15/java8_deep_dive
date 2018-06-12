# java8_deep_dive
. What is the name and URL to the Java base image available in OCP ?<br>
     	a) S2I Builder Image <br>
     	b) redhat-openjdk18-openshift <br>
     	c) Fabric8 Java Base Image OpenJDK 8 (JDK) <br>
     	d) https://github.com/fabric8io-images/java/tree/master/images/jboss/openjdk8/jdk <br>
     	e) https://github.com/jboss-container-images/redhat-openjdk-18-openshift-image <br>
	

. What are all of the environment variables that base image exposes ?
	a) ARTIFACT_DIR - The relative path to the target where JAR files are created for multi-module builds. <br>
	b) JAVA_MAIN_CLASS - The main class to use as the argument to Java. This can also be specified in the .s2i/environment file as a Maven property inside the project (docker.env.Main).<br>
        c) MAVEN_ARGS - The arguments that are passed to the mvn command.<br>



. Where is the existing support documentation for this base Java image ?


. What is the URL to the source code utilized to create this base Java image ?


. What other JBoss middleware builds off of this base image ?


. Is it possible to upload this base Java image (or an image that extends this base Java image) to Docker Hub ?


. What directory path of this base Java image would a deployable "uber" jar need to be added such that it would automatically be picked up at runtime  ?


. What is the directory path to the out of the box shell scripts in that base image that get executed at start-up ?


. What could be the various mechanisms used to add an uber jar to that base java image in an OCP environment ?

