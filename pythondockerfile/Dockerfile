FROM ubuntu:22.04
LABEL devops="anup dudhe"

USER root

RUN apt update 
RUN    apt install python3-pip -y 
RUN    pip3 install virtualenv   
RUN    virtualenv venv 
RUN    source . venv/bin/activate 
RUN    apt update
    
RUN git clone https://github.com/mushfiq1998/string-tools-with-python-django.git && \
    pip install Django 

WORKDIR python-django

RUN python manage.py makemigrations  && \
    python manage.py migrate && \
    python manage.py runserver
    
RUN echo "from django.contrib.auth import get_user_model; User = get_user_model(); User.objects.create_superuser('admin', 'admin@example.com', 'adminpassword')" | python manage.py shell


EXPOSE  8000   

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]  