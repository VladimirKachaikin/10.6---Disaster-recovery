# Домашнее задание к занятию "10.6 Disaster recovery" - Качайкин В.А.

### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозито>
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pa>
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-co>
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.

Желаем успехов в выполнении домашнего задания!

### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

В чём разница между DRaaS, BaaS, Active-Active, Active-Passive?

*Приведите ответ в свободной форме.*

```
DRaaS - это облачный сервис для быстрого восстановления работы серверов в случае аварии или атаки.
Если сервер перестает отвечать, то включается DRaaS, который перемаещает сервер в облачую 
инфракструктуру и позволяет компании продолжать бесперебойно работать.

BaaS - это предоставление организации/пользователю облачного для сервиса для создания резервной копии.

Active-Active - клиентские ПК подключаются к балансировщику нагрузки, который распределяет ресурсы
между несколькими активными серверами.

Active-Passive - клиентские ПК подключаются к главному серверу, который полностью управляет ресурсами. 
Резервный сервер находится в режиме ожидания и активируется только в случае сбоя главного сервера.
```

### Задание 2
Компании нужно составить план восстановления в случае Disaster recovery. 
Сервер состоит из системного диска и диска с данными. Требуется копировать два 
логических диска на один физический:

* системный диск (C:) (20 гигабайт);
* диск с данными (D:) (256 гигабайт).

В требованиях говорится:

* данные критичны в течение 24 часов после аварии;
* сеть критична к большим потокам данных в рабочее время;
* рабочее время с 9.00 до 18.00, пять дней (понедельник – пятница);
* план резервирования должен быть реализован для диска C и для диска D. 
В случае Linux-систем /dev/sda1, /dev/sda4 или /dev/sdb1-данные;
* считается, что для этой задачи может быть: 1) поставлен второй сервер 
или 2) выбрана облачная инфраструктура с определённой услугой;
* компания готова платить за 10 терабайт места как в одном, так и в другом случае.

*Приведите ответ в свободной форме.*

```
Все ПК пользователей находятся в домене сервера, также все виртуальные машины, где запущены сервисы, также находятся в домене. 
Установлен один сервер, на котором работает Acronis Recovery, который полностью делает резервные копирования важных виртуальных машин, 
а также файлового хранилища сети. Резервное делается ежедневно в 23:00. Резервные копии ежедневных резервных копии хранятся 1 месяц, 
потом перезаписываются. В случае сбоя какого-либо сервиса, работащего на виртуальной машине, всегда есть возможность откатиться на версию 
прошлого дня или на версию копии, которая сделана несколько дней назад.
```
![alt text](https://github.com/username/reponame/blob/branch/path/image.png)
