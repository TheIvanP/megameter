FROM python:3.11-slim-buster

RUN /usr/local/bin/python -m pip install --upgrade pip
WORKDIR /usr/src/

COPY requirements.txt requirements.txt

RUN pip install -r requirements.txt

#RUN apt update && apt install net-tools -y

COPY . .

EXPOSE 8080

CMD ["gunicorn", "fapi:app", "-b :8080", "-w 4", "-k uvicorn.workers.UvicornWorker"]

#gunicorn fapi:app -b :8080 -w 4 -k uvicorn.workers.UvicornWorker