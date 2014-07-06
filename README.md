# django_app


Test deployment of Django app with Postgres, Nginx, and Gunicorn

## To deploy
1. vagrant up
2. ansible-playbook -i hosts --private-key=~/.vagrant.d/insecure_private_key site.yml 
