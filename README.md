

# Домашнее задание к занятию "11.4 «Очереди RabbitMQ»" - Соловьёв Андрей SYS-18

---

Работа была выполнена на виртуальной машине с LinuxLite 6.4, организованной с помощью Oracle VM VirtualBox.



## Задание 1. Установка RabbitMQ

Используя Vagrant или VirtualBox, создайте виртуальную машину и установите RabbitMQ. Добавьте management plug-in и зайдите в веб-интерфейс.

Итогом выполнения домашнего задания будет приложенный скриншот веб-интерфейса RabbitMQ.

RabbitMQ установлен  -  apt-get install rabbitmq-server -y --fix-missing

и запущен - systemctl status rabbitmq-server


![RabbitMQ_started.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/RabbitMQ_started.PNG)


скриншот веб-интерфейса RabbitMQ


![RabbitMQ_web.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/RabbitMQ_web.PNG)


## Задание 2. Отправка и получение сообщений

Используя приложенные скрипты, проведите тестовую отправку и получение сообщения. Для отправки сообщений необходимо запустить скрипт producer.py.

![producer.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/producer.PNG)

Для работы скриптов вам необходимо установить Python версии 3 и библиотеку Pika. Также в скриптах нужно указать IP-адрес машины, на которой запущен RabbitMQ, заменив localhost на нужный IP.

Зайдите в веб-интерфейс, найдите очередь под названием hello и сделайте скриншот. После чего запустите второй скрипт consumer.py и сделайте скриншот результата выполнения скрипта

В качестве решения домашнего задания приложите оба скриншота, сделанных на этапе выполнения - 

- запущен producer

![producer_start.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/producer_start.PNG)

- запущен consumer

![Hello_Netology.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/Hello_Netology.PNG)

![consumer_start.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/consumer_start.PNG)


Для закрепления материала можете попробовать модифицировать скрипты, чтобы поменять название очереди и отправляемое сообщение.


![producer_Andrew.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/producer_Andrew.PNG)

![queue_Andrew.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/queue_Andrew.PNG)

![consumer_Andrew.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/consumer_Andrew.PNG)

![consumer_Andrew_started.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/consumer_Andrew_started.PNG)

![consumer_Andrew_recieved.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/consumer_Andrew_recieved.PNG)



## Задание 3. Подготовка HA кластера

Используя Vagrant или VirtualBox, создайте вторую виртуальную машину и установите RabbitMQ. Добавьте в файл hosts название и IP-адрес каждой машины, чтобы машины могли видеть друг друга по имени.


![RabbitMQ_web.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/RabbitMQ_web.PNG)


После этого ваши машины могут пинговаться по имени.

Затем объедините две машины в кластер и создайте политику ha-all на все очереди.

В качестве решения домашнего задания приложите скриншоты из веб-интерфейса с информацией о доступных нодах в кластере и включённой политикой.

Также приложите вывод команды с двух нод:  rabbitmqctl cluster_status


![RabbitMQ_web.PNG](https://github.com/Andrewsolo1969/11-4-hw/blob/master/img/RabbitMQ_web.PNG)


Для закрепления материала снова запустите скрипт producer.py и приложите скриншот выполнения команды на каждой из нод:  rabbitmqadmin get queue='hello'

После чего попробуйте отключить одну из нод, желательно ту, к которой подключались из скрипта, затем поправьте параметры подключения в скрипте consumer.py на вторую ноду и запустите его.

Приложите скриншот результата работы второго скрипта.














 
