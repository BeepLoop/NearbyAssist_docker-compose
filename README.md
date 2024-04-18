# NearbyAssist_docker-compose
Docker compose configuration for NearbyAssist services

## How to use
1. Configure osrm-backend
    - Clone the osrm-backend repo from [here](https://github.com/BeepLoop/osrm-backend)
    - Download OpenStreetMap extract from [Geofabrik](http://download.geofabrik.de/asia/philippines.html)
    - Copy and paste the `.osm.pbf` file to the repo's root directory
    - Follow the repo's instruction under `Using Docker` or run `docker compose up`

2. Configure nearbyassist backend server
    - Clone the server repo from [here](https://github.com/BeepLoop/NearbyAssist/)
    - Configure `.env` file. Follow the example from `.env.example`

3. Configure `env` file for the mysql db. Follow the example from `.env.example`.
4. Update `docker-compose.yml` file
    - Update the mysql db service volume. Point the source `.sql` file to the migrations .sql file from the NearbyAssist server
    - Update the server service build context. Point the context and dockerfile to the NearbyAssist repo directory
    - Update the `env_file` directive under server service to point to the `.env` file of NearbyAssist server

