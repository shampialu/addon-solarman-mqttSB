# https://developers.home-assistant.io/docs/add-ons/configuration#add-on-dockerfile
ARG BUILD_FROM
FROM $BUILD_FROM

WORKDIR /app
ADD . /app

# Install requirements for add-on
RUN apk add --no-cache git curl python3 py3-pip jq
RUN git clone https://github.com/shampialu/solarman-mqtt.git
RUN pip install -r /app/solarman-mqtt/requirements.txt

RUN chmod a+x run.sh

CMD [ "/app/run.sh" ]
