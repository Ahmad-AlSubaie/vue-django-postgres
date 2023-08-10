FROM python:3
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
WORKDIR /django
COPY requirements.txt /django
RUN pip install -r requirements.txt
COPY . /django/
RUN apt-get update && apt-get install -y \
    postgresql-client \
    && rm -rf /var/lib/apt/lists/*
CMD python "manage.py" "runserver" "0.0.0.0:8000" 