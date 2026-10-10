FROM python:3.9-alpine
EXPOSE 8080
WORKDIR /opt/server
COPY requirements.txt .
RUN apk add --no-cache gcc musl-dev linux-headers
RUN pip3 install --prefix=/install -r requirements.txt
COPY . .
ENV CART_HOST="cart" \
    CART_PORT="8080" \
    USER_HOST="user" \
    USER_PORT="8080" \
    AMQP_HOS="rabbitmq" \
    AMQP_USER="roboshop" \
    AMQP_PASS="roboshop123"
CMD ["uwsgi","--ini","payment.ini"]
