FROM python:3.9-slim

LABEL company="Gopenux LAB"
LABEL autor="Nestor Cabrera"

WORKDIR /app/

COPY . . 

RUN pip install -r requirements.txt

EXPOSE 5000

CMD ["python", "app.py"]

