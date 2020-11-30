FROM redis:5.0.6

RUN echo 'deb http://cloudfront.debian.net/debian/ buster main' > /etc/apt/sources.list

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        stunnel \
        python3 \
        python3-pip

RUN python3 -m pip install honcho==1.0.*

ENV PYTHONUNBUFFERED=1
CMD ["honcho", "start", "-f", "/usr/local/etc/redis/redis-tls.proc"]
