# Install Neo4j Enterprise Edition in Ubuntu 100% Work and Simple!

* Install Java if not instal in ubuntu

       sudo apt install openjdk-11-jre-headless -y

* Download Neo4j Enterprise, replace if there is a new version (For now Version 4.4.11)

      wget https://neo4j.com/artifact.php?name=neo4j-enterprise-4.4.11-unix.tar.gz -O neo4j-enterprise-4.4.11-unix.tar.gz

* Un-tar Neo4j Packages

       tar -xvf neo4j-enterprise-4.4.11-unix.tar.gz
    
* Download Plugins for Graph Data Science, APOC, and Bloom.

For Graph Data Science

    wget https://github.com/neo4j/graph-data-science/releases/download/2.1.8/neo4j-graph-data-science-2.1.8.jar
    
For APOC

    wget https://github.com/neo4j-contrib/neo4j-apoc-procedures/releases/download/4.4.0.8/apoc-4.4.0.8-all.jar

For Bloom
   
    wget https://neo4j.com/artifact.php?name=neo4j-bloom-2.4.0.zip -O neo4j-bloom-2.4.0.zip
    
* Edit and insert teks below in conf file path /home/neo4j-enterprise-4.4.11/conf

         dbms.security.procedures.unrestricted=apoc.*,gds.*,bloom.*
         dbms.security.procedures.allowlist=apoc.*,gds.*,bloom.*
         apoc.import.file.enabled=true
         apoc.import.file.use_neo4j_config=true
         dbms.default_listen_address=0.0.0.0
         dbms.default_advertised_address=(YOUR IP)
    
 * Start Neo4j in file path /home/neo4j-enterprise-4.4.11/bin
 
         ./neo4j start
    
