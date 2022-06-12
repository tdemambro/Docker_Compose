Notice: Unable to fetch Public API data from the donordrive site that was provided. I was able to verify that this functionality works with a URL: https://archive.org/wayback/available?url=example.com. However, when attempting to utilize the DonorDrive Public API, no data is ingested into Filebeat. Unsure if using the wrong URL but I was using this URL: https://try.donordrive.com/api/participants/477670

The filebeat.yml file is more of a reference to use when changing the config file on the Filebeat Container (fb-container).

These are the steps that I conducted to get data to upload into filebeats referencing URL https://archive.org/wayback/available?url=example.com:
1. docker-compose up -d
2. docker exec -u 0 -it fb-container bash (I do this to get into the Filebeat container to set up the filebeat configuration)
3. apt update (necessary steps to install editing tools)
4. apt upgrade (necessary steps to install editing tools)
5. apt install wget gpg vim (tools that may need to be used to edit the files)
6. FB-Container should have a filebeat.yml file within it at /usr/share/filebeat#
7. vi filebeat.yml - Set config file to mimic what is in the filebeat.yml file within this repo:
8. Save and Exit out of VI editor
9. filebeat setup -e
10. Graphs with data should become visible on elasticsearch (http://localhost:5601)
