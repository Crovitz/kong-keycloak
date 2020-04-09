# kong configuration

1. build docker image

	```docker build -it kong:test-1```

2. deploy docker stack

	```docker stack deploy -c docker-internal.yml sample-stack```

3. open localhost:1337 (konga)

	create admin user

4. connect to kong

	kong admin url: http://kong:8001

5. create service

	name: sample-service
  
	url: http://192.168.1.26:8080

6. create route

	name sample-route
  
	paths: /sample
  
	strip_path: true

7. test routing

	if sample api is: http://192.168.1.26:8080/dictionaries
  
	make request to: http://192.168.1.26:8000/sample/dictionaries

8. activate jwt-keycloak plugin to test security

	(remember to use local address of machine not localhost in docker swarm (eg. 192.168.1.26))
