FROM python:3.11
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
WORKDIR /app
COPY requirements.txt /app/
RUN pip install -r requirements.txt
COPY . /app/

CMD ["sh", "-c", "python manage.py migrate && gunicorn product_service.wsgi:application --bind 0.0.0.0:$PORT"]