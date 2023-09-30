# Отчет по практическому заданию "Идентификация и аутентификация"

# Задача

1) Создать виртуальную машину на базе Kali Linux.
2) Создать пользователя super-{Pankov.N.O} и наделить его привилегиями суперпользователя.
3) Создать группу group-{1}.
4) Добавить пользователя super-{Pankov.N.O} в группу group-{1}.
5) Проверить наличие пользователя в группе.
6) Создать пользователя user-{Pankov.N.O} и добавить его в группу group-{1}.
7) Наделить полномочиями пользователя user-{Pankov.N.O} по созданию и удалению файлов в домашнем каталоге пользователя super-{Pankov.N.O} с использованием механизма разграничения доступа chmod.
8) Продемонстрировать работу механизмов разграничения доступа.

# Шаги выполнения

```bash
# Шаг 2
root@mrx:~# useradd super-{Pankov.N.O}
root@mrx:~# passwd super-{Pankov.N.O}
root@mrx:~# usermod -aG sudo super-{Pankov.N.O}

# Шаг 3
root@mrx:~# groupadd group-{1}

# Шаг 4
root@mrx:~# usermod -aG group-{1} super-{Pankov.N.O}

# Шаг 5
root@mrx:~# groups super-{Pankov.N.O}

# Шаг 6
root@mrx:~# useradd user-{Pankov.N.O}
root@mrx:~# usermod -aG group-{1} user-{Pankov.N.O}

# Шаг 7
root@mrx:~# chmod 770 /home/super-{Pankov.N.O}
root@mrx:~# chown super-{Pankov.N.O}:group-{1} /home/super-{Pankov.N.O}

# Шаг 8
$ su user-{Pankov.N.O}
$ touch /home/super-{Pankov.N.O}/test_file.txt
$ rm /home/super-{Pankov.N.O}/test_file.txt
```
[Скриншот - Команды в терминале ]

![Скриншот 2 - Команды в терминале ](https://i.imgur.com/BcqrWBS.jpeg)
