CONTAINER_NAME=ferimer/melt

build_stretch:
	docker build -t ${CONTAINER_NAME}:stretch_builder -f Dockerfile.stretch .

build_buster:
	docker build -t ${CONTAINER_NAME}:buster_builder -f Dockerfile.buster .

run_stretch: build_stretch
	docker run --rm --mount type=volume,src=melt_stretch,dst=/root/melt ${CONTAINER_NAME}:stretch_builder

run_buster: build_buster:
	docker run --rm --mount type=volume,src=melt_buster,dst=/root/melt ${CONTAINER_NAME}:buster_builder

publish_stretch: build_stretch
	docker push ${CONTAINER_NAME}:stretch_builder

publish_buster: build_buster
	docker push ${CONTAINER_NAME}:buster_builder

clean:
	docker image rm ${CONTAINER_NAME}:stretch_builder
	docker image rm ${CONTAINER_NAME}:buster_builder

publish: publish_stretch publish_buster
