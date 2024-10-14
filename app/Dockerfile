ARG PYTHON_VERSION=3.9
FROM python:${PYTHON_VERSION}-alpine

RUN adduser -H -D -u 1000 appuser

WORKDIR /app

COPY ./requirements.txt .
RUN pip install -r requirements.txt

COPY . .
RUN chown -R appuser:appuser /app

USER appuser
CMD python app.py
