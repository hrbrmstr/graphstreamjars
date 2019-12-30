.PHONY: clean pkg deps run

pkg:
	mvn --quiet package
	cp target/graphstreamjars-1.0-SNAPSHOT.jar ../../inst/java
	cp deps/*.jar ../../inst/java

clean:
	mvn clean

deps:
	mvn dependency:copy-dependencies -DoutputDirectory=deps

new:
	mv pom.xml /tmp
	mvn archetype:generate -DgroupId=is.rud.graphstreamjars -DartifactId=graphstreamjars -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
	mv /tmp/pom.xml .
