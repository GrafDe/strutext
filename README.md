strutext
========

Library of text structuration components

Для работы библиотеки нужно установить (Ubuntu Linux):

1) CMake - sudo apt-get install cmake

2) BoostLibs - sudo apt-get install libboost-all-dev

3) Log4cplus:

Переходим в директорию для исходных файлов
# cd /usr/local/src
Скачиваем пакет:
# sudo wget http://downloads.sourceforge.net/project/log4cplus/log4cplus-stable/1.1.1/log4cplus-1.1.1.tar.bz2
Устанавливаем log4cplus
# cd /usr/local/src
# tar xjf log4cplus-1.1.1.tar.bz2
# cd log4cplus-1.1.1
# ./configure --prefix=/usr/local/log4cplus-1.1.1
# make
# make install
# ln -s /usr/local/log4cplus-1.1.1 /usr/local/log4cplus
