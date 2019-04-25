# lealni_infra
lealni Infra repository

##Home Work №3

Параметры подключения:
```
bastion_IP = 35.228.175.1
someinternalhost_IP = 10.166.0.4
```

Для подключения к серверу во внутренней сети в одну команду необходимо выполнить следующее:

1. Запустить ssh-agent
```exec ssh-agent bash``` (для CentOS)) если не запущен
2. Добавить приватный ключ в ssh агент
```ssh-add ~/.ssh/appuser```
3. Можно подлючаться
```ssh -A appuser@35.228.175.1 -t 'ssh 10.166.0.4'```

Подключение с локального АРМ к серверу во внутренеей сети:

1. Создать конфигурационый файл ssh
```touch ~/.ssh/config```
2. Внести в файл следующую информацию
```
Host bastion       
ForwardAgent yes
Hostname 35.228.175.1
User appuser

Host someinternalhost 
ProxyCommand ssh -q bastion nc -q0 10.166.0.4 22
```

##Home Work №4

Параметры подключения:
```
testapp_IP = 35.228.175.
testapp_port = 9292
```
