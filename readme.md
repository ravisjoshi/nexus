docker run --rm -d --name nexus -p 8081:8081 -p 8082:8082 -p 8083:8083 -v /Users/ac31613/Testing/nexus-data:/nexus-data sonatype/nexus3


* mvn clean
* mvn clean install
* mvn deploy -s ./settings.xml



If something fails, check if any of the below are missing:-
* Create 2 hosted repositories
    * ravi-snapshots —> VersionPolicy: Snapshot, AllowRedeploy
    * ravi-releases  —> VersionPolicy: Release, DenyRedeploy
* Create 2 proxy repositories:
    * ravi-proxy-snapshots —> VersionPolicy: Snapshot, RemoteStorage: https://repo1.maven.org/maven2/
    * ravi-proxy-releases  —> VersionPolicy: Release, RemoteStorage: https://repo1.maven.org/maven2/

* Update pom.xml
* Create/update settings.xml


