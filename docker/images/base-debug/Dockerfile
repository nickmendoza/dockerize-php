# phpexperts/php:7-base-debug
FROM phpexperts/php:7

ARG PHP_VERSION=7.4

COPY xdebug.conf /tmp

RUN apt-get update && \
    apt-get install -y php-xdebug && \

    # Configure XDebug
    cat /tmp/xdebug.conf >> /etc/php/${PHP_VERSION}/mods-available/xdebug.ini && \
    rm /tmp/xdebug.conf && \

    # Cleanup
    apt-get remove -y && \
    apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
