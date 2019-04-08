FROM wurstmeister/kafka

ENV KAFKA_USER=kafka \
    KAFKA_HOME=/opt/kafka
    
RUN set -x \
    && adduser $KAFKA_USER -D \
    && chmod 755 /usr/bin/start-kafka.sh /usr/bin/broker-list.sh /usr/bin/create-topics.sh /usr/bin/versions.sh \
    && chown -R "$KAFKA_USER:0" $KAFKA_HOME $KAFKA_HOME/config \
    && chgrp -R 0 $KAFKA_HOME $KAFKA_HOME/config \
    && chmod -R g=u $KAFKA_HOME $KAFKA_HOME/config 

USER $KAFKA_USER

# Use "exec" form so that it runs as PID 1 (useful for graceful shutdown)
CMD ["start-kafka.sh"]
