FROM python:3.7-slim-buster

WORKDIR /app
RUN pip install poetry

ADD poetry.lock .
ADD pyproject.toml .

RUN poetry install --no-dev

COPY .ci/entrypoint.sh .
COPY src ./src

ENTRYPOINT ["/app/entrypoint.sh"]