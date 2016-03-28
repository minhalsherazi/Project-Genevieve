# Project-Genevieve
SDN based firewall in OpenDaylight controller
This application is built on OpenDaylight tutorial provided on sdnhub.

#HOW TO BUILD
In order to build first all the it's required to be in the vm provided by SDNHUB (which can be found here: http://yuba.stanford.edu/~srini/tutorial/SDN_tutorial_VM_64bit.ova). Rename code file to "L2 forwarding switch" and place it in the L2 adsl switch forwarding directory. In order to run it is a requirement to have JDK 1.8+ and Maven 3.2+. The following commands are used to build and run.

$ mvn clean install
$ cd distribution/opendaylight-karaf/target/assembly
$ ./bin/karaf
karaf>feature:install sdnhub-XYZ

# Directory Organization for the downloaded vm:
pom.xml: The POM in the main directory specifies all the sub-POMs to build.
commons/parent: contains the parent pom.xml with all properties defined for the subprojects.
commons/utils: contains custom utilities built for OpenFlow programming.
learning-switch: contains the tutorial L2 hub / switch.
tapapp: contains the traffic monitoring tap application.
features: defines the two features "sdnhub-tutorial-learning-switch", * "sdnhub-tutorial-tapapp" that can be loaded in Karaf.
distribution/karaf-branding: contains karaf branner for SDN Hub
distribution/opendaylight-karaf: contains packaging relevant pom to * generate a running directory.
