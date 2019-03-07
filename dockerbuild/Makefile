ROOT=$(shell realpath ..)

HOST_DIR=${ROOT}
GUEST_DIR=/build/
TAG=genivi-builder
TARGET=qemux86-64
USER=$(shell stat -c "%u:%g" .)

.PHONY: genivi
genivi:
	docker run -v ${HOST_DIR}:${GUEST_DIR} -w ${GUEST_DIR} -u ${USER} ${TAG} bash -c "source init.sh ${TARGET} ; pwd; bitbake -D genivi-dev-platform"

.PHONY: docker
docker:
	docker build -t $(TAG) docker

