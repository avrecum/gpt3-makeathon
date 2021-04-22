FROM python:latest
WORKDIR /usr/src/app
RUN pip install --upgrade pip

COPY . /usr/src/app

RUN CFLAGS="-Wno-narrowing" pip install cld2-cffi
RUN pip install -r requirements.txt
RUN python configure_nltk.py
EXPOSE 5000
CMD ["uvicorn", "index:app", "--host", "0.0.0.0" ,"--port", "5000", "--log-level", "info"]



