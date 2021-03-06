---
title: Virtual Environments
localeTitle: Виртуальная среда
---
## Виртуальные сети

Виртуальные среды можно охарактеризовать как изолированные установочные каталоги. Эта изоляция позволяет локализовать установку зависимостей вашего проекта, не заставляя вас устанавливать их в рамках всей системы.

Представьте, что у вас есть два приложения App1 и App2. Оба требуют пакет Pak, но с разными версиями. Если вы установите Pak версии 2.3 для App1, вы не сможете запустить App2, потому что для него требуется версия 3.1. Вот когда вам пригодится виртуальная среда.

Выгоды:

*   Вы можете иметь несколько сред, с несколькими наборами пакетов, без конфликтов между ними. Таким образом, требования разных проектов могут быть выполнены одновременно.
*   Вы можете легко отпустить свой проект со своими зависимыми модулями.

Вот два способа создания виртуальных сред Python.

## Virtualenv

[`virtualenv`](https://virtualenv.pypa.io/en/stable/) - это инструмент, используемый для создания изолированных сред Python. Он создает папку, содержащую все необходимые исполняемые файлы, для использования пакетов, которые потребуются для проекта Python.

Вы можете установить его с помощью `pip` :
```
pip install virtualenv 
```

Проверьте установку с помощью следующей команды:
```
virtualenv --version 
```

### Создание среды

Чтобы создать виртуальную среду, используйте:
```
virtualenv --no-site-packages my-env 
```

Это создает папку в текущем каталоге с именем среды ( `my-env/` ). Эта папка содержит каталоги для установки модулей и исполняемых файлов Python.

Вы также можете указать версию Python, с которой хотите работать. Просто используйте аргумент `--python=/path/to/python/version` . Например, `python2.7` :
```
virtualenv --python=/usr/bin/python2.7 my-env 
```

### Среда списка

Вы можете указать доступные среды:
```
lsvirtualenv 
```

### Активировать среду

Прежде чем вы сможете начать использовать среду, вам необходимо активировать ее:
```
source my-env/bin/activate 
```

Это гарантирует, что будут использоваться только пакеты под `my-env/` .

Вы заметите, что имя среды отображается слева от подсказки. Таким образом, вы можете видеть, какая из них активна.

### Установить пакеты

Вы можете устанавливать пакеты один за другим или устанавливая файл `requirements.txt` для своего проекта.
```
pip install some-package 
 pip install -r requirements.txt 
```

Если вы хотите создать файл `requirements.txt` из уже установленных пакетов, выполните следующую команду:
```
pip freeze > requirements.txt 
```

Файл будет содержать список всех пакетов, установленных в текущей среде, и их соответствующие версии. Это поможет вам выпустить свой проект с помощью собственных зависимых модулей.

### Деактивировать среду

Если вы закончили работу с виртуальной средой, вы можете деактивировать ее с помощью:
```
deactivate 
```

Это вернет вас к интерпретатору Python по умолчанию со всеми его установленными библиотеками.

### Удалить среду

Просто удалите папку окружения.

## Конда

[`Conda`](https://conda.io/docs/index.html) - это пакет, зависимость и управление средой для многих языков, включая Python.

Чтобы установить Conda, следуйте этим [инструкциям](https://conda.io/docs/user-guide/install/index.html) .

### Создание среды

Чтобы создать виртуальную среду, используйте:
```
conda create --name my-env 
```

Conda создаст соответствующую папку в каталоге установки Conda.

Вы также можете указать, с какой версией Python вы хотите работать:
```
conda create --name my-env python=3.6 
```

### Среда списка

Вы можете перечислить все доступные среды:
```
conda info --envs 
```

### Активировать среду

Прежде чем вы сможете начать использовать среду, вам необходимо активировать ее:
```
source activate my-env 
```

### Установить пакеты

То же, что и с `virtualenv` .

### Деактивировать среду

Если вы закончили работу с виртуальной средой, вы можете деактивировать ее с помощью:
```
source deactivate 
```

### Удаление среды

Если вы хотите удалить среду из Conda, используйте:
```
conda remove --name my-env 
```

#### Дополнительная информация:

*   [Официальный сайт](https://virtualenv.pypa.io/en/stable/) `virtualenv`
*   [Официальный сайт](https://conda.io/docs/index.html) `Conda`
*   `The Hitchhicker's Guide to Python` - [Pypenv & Virtual Environments](http://docs.python-guide.org/en/latest/dev/virtualenvs/)