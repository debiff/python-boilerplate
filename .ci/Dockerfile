FROM python:3.7.0

WORKDIR /app
RUN pip install poetry

ADD poetry.lock .
ADD pyproject.toml .

RUN poetry install --no-dev

COPY src .

ENTRYPOINT ["entrypoint.sh"]
CMD