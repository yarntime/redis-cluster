FROM docker.io/ruby:2.2.2

WORKDIR /opt/redis/

RUN wget https://rubygems.global.ssl.fastly.net/gems/redis-3.2.1.gem \
    && gem install -l ./redis-3.2.1.gem

RUN wget https://github.com/antirez/redis/archive/3.0.1.tar.gz \
    && tar -xzvf 3.0.1.tar.gz \
    && cd redis-3.0.1   \
    && make && make install \
    && cd .. && rm -rf 3.0.1.tar.gz

RUN mkdir /data

VOLUME /data
WORKDIR /data

EXPOSE 6379 16379

ENTRYPOINT ["redis-server"]