FROM 32bit/ubuntu:16.04

RUN apt-get update && apt-get install -y socat
RUN groupadd ctf

RUN mkdir /rev

COPY enc.out /rev/enc
COPY flag.txt /rev/
COPY entry.sh /rev/entry.sh

RUN useradd -G ctf --home=/rev revuser
RUN useradd -G ctf --home=/rev revflag

RUN chown revflag:revflag /rev/enc
RUN chown revflag:revflag /rev
RUN chown revflag:revflag /rev/flag.txt

RUN chmod 4755 /rev/enc
RUN chmod 4755 /rev/entry.sh
RUN chmod 444 /rev/flag.txt

EXPOSE 30049
ENTRYPOINT ["/rev/entry.sh"]
