appd-ma

This is a simple version of the docker machine agent without docker compose.

clone this repo
download the appdynamics machine agent.  copy it into this directory and rename it to machineagent.zip
modify the appdynamics.env to setup your agent environment variables

Build image
	docker build -t someone/appdma:4.4 .

Run Image
	docker container run -d --name appdma --env-file appdynamics.env -v /:/hostroot:ro -v /var/run/docker.sock:/var/run/docker.sock someone/appdma:4.4 

If you need to inspect the image, logs are under /opt/appdynamics/machine-agent/logs
	docker exec -it appdma bash
