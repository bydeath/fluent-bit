FROM amd64/debian:buster-slim

RUN apt-get update && apt-get install -y --no-install-recommends build-essential curl cmake make tar pkg-config libsystemd-dev zlib1g-dev libpq-dev flex bison

WORKDIR cio

COPY . .
RUN cmake . && make

CMD tools/cio -p "tests/data/1.5kb.txt" -v -e 2000 -w 10000