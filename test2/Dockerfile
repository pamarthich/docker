FROM test-java:1.1
RUN wget --no-check-certificate -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | apt-key add - \
    && apt-get install apt-transport-https -y \
    && echo "deb https://artifacts.elastic.co/packages/6.x/apt stable main" | tee -a /etc/apt/sources.list.d/elastic-6.x.list \
    && apt-get update \
    && apt-get install logstash -y
COPY output_filter.conf /etc/logstash/output_filter.conf
COPY input_filter.conf /etc/logstash/input_filter.conf

