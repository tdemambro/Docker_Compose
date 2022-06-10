# Attempt to utilize docker-compose feature to spin up multiple docker containers.
# Verified ability to run docker-compose up -d and images for filebeat, kibana and elasticsearch spin up. Verified ability to access elasticsearch via localhost
# Verified by running docker-compose logs -f that data is registering from the containers themselves.
# Issues with incorporating filebeat.input to ingest httpjson log data (or any data in general) that can be sent to elasticsearch, unsure if docker-compose will work with this request.
