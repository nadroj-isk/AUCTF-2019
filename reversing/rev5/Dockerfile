FROM ubuntu:latest

RUN apt update
RUN apt install -y socat 
RUN groupadd ctf

RUN mkdir /rev

COPY rev5 /rev/
COPY flag.txt /rev/
COPY entry.sh /rev/entry.sh

RUN useradd -G ctf --home=/rev revuser
RUN useradd -G ctf --home=/rev revflag

RUN chown revflag:revflag /rev/rev5
RUN chown revflag:revflag /rev
RUN chown revflag:revflag /rev/flag.txt

RUN chmod 4755 /rev/rev5
RUN chmod 4755 /rev/entry.sh
RUN chmod 444 /rev/flag.txt

EXPOSE 7001
ENTRYPOINT ["/rev/entry.sh"]
