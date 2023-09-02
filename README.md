## SONARQUBE SERVER WITH POSTGRESQL DATABASE


#### To run the containers in detached mode :
    docker-compose up -d
    
##### Access web ui on http://localhost:9000
##### Login : admin Password : admin


### COMMON ERROR IF YOU ARE USING LINUX :
bootstrap check failure [1] of [1]: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]

### SOLLUTION:
-  Locate the configuration file where kernel parameters are set. On most Linux systems, this file is /etc/sysctl.conf

- Add the following line to the configuration file to set vm.max_map_count to the minimal required value (262144) vm.max_map_count=262144

        sudo echo "vm.max_map_count=262144" >> /etc/sysctl.conf


- Apply the Changes

        sudo sysctl -p
        

- Restart your SonarQube and PostgreSQL containers:

        docker-compose down
        docker-compose up -d