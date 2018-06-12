# java8_deep_dive
. What is the name and URL to the Java base image available in OCP ?<br>
     	a) S2I Builder Image <br>
     	b) redhat-openjdk18-openshift <br>
     	c) Fabric8 Java Base Image OpenJDK 8 (JDK) <br>
     	d) https://github.com/fabric8io-images/java/tree/master/images/jboss/openjdk8/jdk <br>
     	e) https://github.com/jboss-container-images/redhat-openjdk-18-openshift-image <br>
	

. What are all of the environment variables that base image exposes ? <br>
* **ARTIFACT_DIR** - The relative path to the target where JAR files are created for multi-module builds. <br>
* **JAVA_MAIN_CLASS** - The main class to use as the argument to Java. This can also be specified in the .s2i/environment file as a Maven property inside the project (docker.env.Main).<br>
* **MAVEN_ARGS** - The arguments that are passed to the mvn command.<br>
* **JAVA_APP_DIR** the directory where the application resides. All paths in your application are relative to this directory. By default it is the same directory where this startup script resides.
* **JAVA_LIB_DIR** directory holding the Java jar files as well an optional `classpath` file which holds the classpath. Either as a single line classpath (colon separated) or with jar files listed line-by-line. If not set **JAVA_LIB_DIR** is the same as **JAVA_APP_DIR**.
* **JAVA_OPTIONS** options to add when calling `java`
* **JAVA_MAJOR_VERSION** can be 7,8 or 9. If the version is set then only options suitable for this version are used. Actually only 7 is required to set to remove some options known only to Java > 8
* **JAVA_MAX_MEM_RATIO** is used when no `-Xmx` option is given in `JAVA_OPTIONS`. This is used to calculate a default maximal Heap Memory based on a containers restriction. If used in a Docker container without any memory constraints for the container then this option has no effect. If there is a memory constraint then `-Xmx` is set to a ratio of the container available memory as set here. The default is `25` when the maximum amount of memory available to the container is below 300M, `50` otherwise, which means in that case that 50% of the available memory is used as an upper boundary. You can skip this mechanism by setting this value to 0 in which case no `-Xmx` option is added.
* **JAVA_INIT_MEM_RATIO** is used when no `-Xms` option is given in `JAVA_OPTIONS`. This is used to calculate a default initial Heap Memory based on a containers restriction. If used in a Docker container without any memory constraints for the container then this option has no effect. If there is a memory constraint then `-Xms` is set to a ratio of the container available memory as set here. By default this value is not set.
* **JAVA_MAX_CORE** restrict manually the number of cores available which is used for calculating certain defaults like the number of garbage collector threads. If set to 0 no base JVM tuning based on the number of cores is performed.
* **JAVA_DIAGNOSTICS** set this to get some diagnostics information to standard out when things are happening
* **JAVA_MAIN_CLASS** A main class to use as argument for `java`. When this environment variable is given, all jar files in `$JAVA_APP_DIR` are added to the classpath as well as `$JAVA_LIB_DIR`.
* **JAVA_APP_JAR** A jar file with an appropriate manifest so that it can be started with `java -jar` if no `$JAVA_MAIN_CLASS` is set. In all cases this jar file is added to the classpath, too.
* **JAVA_APP_NAME** Name to use for the process
* **JAVA_CLASSPATH** the classpath to use. If not given, the startup script checks for a file `${JAVA_APP_DIR}/classpath` and use its content literally as classpath. If this file doesn't exists all jars in the app dir are added (`classes:${JAVA_APP_DIR}/*`).
* **JAVA_DEBUG** If set remote debugging will be switched on
* **JAVA_DEBUG_SUSPEND** If set enables suspend mode in remote debugging
* **JAVA_DEBUG_PORT** Port used for remote debugging. Default: 5005


. Where is the existing support documentation for this base Java image ? <br>
        a) https://docs.openshift.com/online/using_images/s2i_images/java.html <br>

. What is the URL to the source code utilized to create this base Java image ?


. What other JBoss middleware builds off of this base image ?


. Is it possible to upload this base Java image (or an image that extends this base Java image) to Docker Hub ?


. What directory path of this base Java image would a deployable "uber" jar need to be added such that it would automatically be picked up at runtime  ?


. What is the directory path to the out of the box shell scripts in that base image that get executed at start-up ?


. What could be the various mechanisms used to add an uber jar to that base java image in an OCP environment ?

