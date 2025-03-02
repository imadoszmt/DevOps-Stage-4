FROM python:3.9

WORKDIR /app

COPY requirements.txt .
RUN apt-get update && apt-get install -y gcc python3-dev

COPY . .

CMD ["python", "main.py"]
