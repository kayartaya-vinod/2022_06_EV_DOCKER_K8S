FROM python:alpine

WORKDIR /vinod/workdir

COPY ./requirements.txt ./

RUN python -m pip install -r ./requirements.txt

COPY ./main.py ./
COPY ./mydb.sqlite3 ./

EXPOSE 8080

ENTRYPOINT ["python", "main.py"]

