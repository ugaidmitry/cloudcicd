Регистрация Gitlab Runner и запуск простейшего пайплайна
Цель: Научиться запускать runner, понять основные концепции разработки пайплайнов и механизма их выполнения
Для выполнения домашнего задания потребуется репозиторий с форком выбранного проекта(если не определились с 
выбором - можно сделать форк https://gitlab.com/SablinIgor/crate ) на gitlab.com
1) сделать форк репозитория
2) запустить и привязать к проекту gitlab-runner
3) написать простейший .gitlab-ci.yml пайплайн по примерам из документации
4) добиться успешного выполнения пайплайна

Решение: Сампайплайн проходит в gitlab локальный далее docker образы он пушит в azure registry

1)Сделал форк git clone https://gitlab.com/SablinIgor/crate
2)Установил https://bitnami.com/stack/gitlab/virtual-machine - досупна по dima.com -https://github.com/ugaidmitry/cloudcicd/blob/master/hw6/gitlab.png

https://github.com/ugaidmitry/cloudcicd/blob/master/hw6/dns.png  -dns установил

3)Создал самоподписанный сертификат dima-com.pem

4)в локальной сети создал dns запись на dima.com 

5)создал еще одну vm - gitrunner - скопировал туда сертификат и зарегестрировал раннер
  sudo gitlab-runner register --tls-ca-file dima-com.pem
  https://github.com/ugaidmitry/cloudcicd/blob/master/hw6/runner.png
  
  
6)поправил .gitlab-ci.yml и конфиг скрипты  -https://github.com/ugaidmitry/cloudcicd/blob/master/hw6/.gitlab-ci.yml

7)https://github.com/ugaidmitry/cloudcicd/blob/master/hw6/passed.png - выполнил пайплайн
  
