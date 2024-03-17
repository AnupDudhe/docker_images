FROM ubuntu:22.04
LABEL devops="anup dudhe"

USER root

RUN apt=get update  && \
    apt-get install python3-pip && \
    pip3 install virtualenv && \ 
    virtualenv venv && \
    source venv/bin/activate && \
    sudo apt update
    
RUN git clone https://github.com/mushfiq1998/string-tools-with-python-django.git && \
    pip install Django 

WORKDIR python-django

RUN python manage.py makemigrations  && \
    python manage.py migrate && \
    python manage.py runserver
    
RUN echo "from django.contrib.auth import get_user_model; User = get_user_model(); User.objects.create_superuser('admin', 'admin@example.com', 'adminpassword')" | python manage.py shell


EXPOSE  8000   

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]  