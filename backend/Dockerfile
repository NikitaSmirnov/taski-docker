FROM python:3.11

WORKDIR /app

RUN pip install --default-timeout=100 --upgrade pip

RUN pip install gunicorn==20.1.0 --default-timeout=100

COPY requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir --default-timeout=100

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]