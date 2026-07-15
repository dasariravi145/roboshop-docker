FROM python:3.9.25-alpine3.22 AS builder
WORKDIR /app
RUN apk add --no-cache build-base linux-headers pcre-dev
COPY requirements.txt .
RUN pip3.0 install --prefix=/install -r requirements.txt

FROM python:3.9.25-alpine3.22
EXPOSE 8080
WORKDIR /app
RUN apk add --no-cache pcre
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
COPY --from=builder /install /usr/Local
COPY --chown=roboshop:roboshop payment.ini *.py requirements.txt .
USER roboshop
CMD ["uwsgi", "--ini", "payment.ini"]