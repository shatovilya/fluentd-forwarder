FROM fluent/fluentd:v1.15-1
LABEL maintainer="Shatov Ilya https://github.com/shatovilya"

USER root

# below RUN includes plugin as examples elasticsearch is not required
# you may customize including plugins as you wish
RUN apk add --no-cache --update --virtual .build-deps \
        sudo build-base ruby-dev \
 && sudo gem install elasticsearch -v 7.10.1 \
 && sudo gem install gelf \
 && sudo gem install fluent-plugin-prometheus \
 && sudo gem install fluent-plugin-elasticsearch \
 && sudo gem install fluent-plugin-secure-forward \
 && sudo gem install fluent-plugin-http-healthcheck \
 && sudo gem sources --clear-all \
 && apk del .build-deps \
 && rm -rf /home/fluent/.gem/ruby/2.7.6/cache/*.gem

COPY ./plugins /fluentd/plugins

#COPY ./fluent.conf /fluentd/etc/fluent.conf

COPY entrypoint.sh /bin/

RUN chmod +x /bin/entrypoint.sh

USER fluent