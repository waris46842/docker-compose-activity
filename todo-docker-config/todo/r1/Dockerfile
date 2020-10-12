FROM python:3.7-buster

WORKDIR /root
RUN git clone https://github.com/natawutn/todo.git
WORKDIR /root/todo
RUN git checkout tags/release-1
RUN pip install uvicorn
RUN pip install fastapi
RUN pip install poetry
RUN POETRY_version=0.12.3 curl -sSL https://raw.githubusercontent.com/sdispater/poetry/master/get-poetry.py | python
ENV PATH=/root/.poetry/bin:$PATH
RUN poetry config virtualenvs.create false
# RUN poetry install

EXPOSE 8000
CMD  python -m uvicorn --host=0.0.0.0 --port=8000 --reload todo.main:app