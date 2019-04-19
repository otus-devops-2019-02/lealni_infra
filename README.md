# lealni_infra
lealni Infra repository

Параметры подключения:
```
bastion_IP = 35.228.175.1
someinternalhost_IP = 10.166.0.4
```

Для подключения к серверу во внутренней сети в одну команду необходимо выполнить следующее:
```
1. Запустить ssh-agent (
    a. exec ssh-agent bash (для CentOS)) если не запущен
2. Добавить приватный ключ в ssh агент
    a. ssh-add ~/.ssh/appuser
3. Можно подлючаться
    a. ssh -A appuser@35.228.175.1 -t 'ssh 10.166.0.4'
```
