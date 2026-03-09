# Домашнее задание к занятию «Хранение в K8S»

## Задание 1

Проверка вывода *index.html* в Nginx при помощи команды `curl`:

![Ответ на задание 1](https://github.com/Francotirado/kuber-5/blob/main/img/1.jpg)

Ссылка на манифесты:

[deployment.yml](https://github.com/Francotirado/kuber-5/blob/main/configMap/deployment.yml)

[configmap-web.yml](https://github.com/Francotirado/kuber-5/blob/main/configMap/configmap-web.yml)

## Задание 2

Проверка работы Nginx с протоколом HTTPS через браузер на хостовой машине:

![Ответ на задание 2](https://github.com/Francotirado/kuber-5/blob/main/img/2.jpg)

Ссылка на манифесты:

[secret-tsl.yml](https://github.com/Francotirado/kuber-5/blob/main/https/secret-tsl.yml)

[ingress.yml](https://github.com/Francotirado/kuber-5/blob/main/https/ingress.yml)

## Задание 3

Проверка разграничения прав при помощи RBAC:

![Ответ на задание 3](https://github.com/Francotirado/kuber-5/blob/main/img/3.jpg)

Использованные команды для генерации сертификатов (предварительно сертификаты кластера K8S были скопированы в рабочую директорию):

```
openssl genrsa -out developer.key 2048
openssl req -new -key developer.key -out developer.csr -subj "/CN=developer"
openssl x509 -req -in developer.csr -CA ca.crt -CAkey ca.key -CAcreateserial -out developer.crt -days 365
```

Ссылка на манифесты:

[role-pod-reader.yml](https://github.com/Francotirado/kuber-5/blob/main/rbac/role-pod-reader.yml)

[rolebinding-developer.yml](https://github.com/Francotirado/kuber-5/blob/main/rbac/rolebinding-developer.yml)

