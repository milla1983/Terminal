**README.md**
***
1.Посмотеть где я
+ `pwd`  

2.Создать папку  
+ `mkdir folder`  
+ `rm folder` - удалить пустую папку 
+ `rm -r folder` - удалить папку с файлами внутри 

3.Зайтив папку
+ `cd c:/` — перейти в конкретный диск
+ `cd !$` — перейти в только что созданную папку
+ `cd folder`
+ `cd ~/Documents/group_29/folder` — полный путь
+ если в названии каталога есть пробелы, их нужно экранировать  
используя "\" `(cd /folder/новая\ папка/)` или обернуть путь в кавычки `cd "/folder/новая папка/" ` 

4.Создать 3 папки 
+ `mkdir folder1 folder2 folder3`
+ `mkdir folder{1..3}` 

для создания вложенных папок — `mkdir -p folder{1..5}/folder_{1..3}` 
или —` mkdir -p folder/folder1/folder2` 

5.Зайти в папку
+ `cd folder1`
6.Создать 5 файлов (3 txt, 2 json)
+ `touch {name1.txt,name2.txt,name3.txt,name1.json,name2.json}`
+ `touch name1.txt name2.txt name3.txt name1.json name2.json`
+ `touch name{1..3}.txt name{1..2}.json`
`file name2.json` — узнать информацию о типе файла 

7.Создать 3 папки
+ `mkdir folder_1 folder_2 folder_3`
+ или —` mkdir folder_{1..3}` 

8.Вывести содержимое директории
+ `ls`
+ `ls -l` — выведет список файлов построчно
+ `ls -F` с отображением типа файла 
+ `ls -aF` — выведет все файлы и их тип
+ `ls -r` — с сортировкой в обратном порядке
+ `ls -R` — вместе с содержимым поддиректорий
+ `ls -A` — влючая скрытые файлы (файлы с точкой перед названием)
+ `ls -lAh` — с отображением размера файлов
+ `ls -lSh` — с сортировкой по размеру файлов и его отображением
+ `ls -ld */` — отобразит только вложенные директории внутри текущей
+ `ls -lt` — с сортировкой по дате создания файлов
+ `ls -lu` — с сортировкой по дате обращения к файлам
+ `ls -la` — расширенный вывод всех файлов (разрешения, владелец, размер, дата изменения) 

9.Открыть любой txt файл
+ `vim name1.txt` 

10.Добавить любой текст
+ `i` — перейти в режим редактирования

11.Сохранить и выйти из vim
+ `esc` — выйти из режима редактирования
+ `:wq` — записать изменения и выйти из vim 

12.Выйти из папки на уровень выше
+ `cd ..`
+ `cd -`
+ `cd ../..` — на 2 уровня вверх 

13.Переместить любые 2 файла, которые вы создали, в любую другую папку
+ `mv folder1/{name2.txt,name1.json} folder1/folder_1`
+ `mv folder1/*.* folder2` — переместить все файлы из папки app1 в папку app2 

14.Скопировать любые 2 файла, которые вы создали, в любую другую папку
+ `cp folder1/{name3.txt,name2.json} folder1/folder_2` 

15.Найти файл по имени
+ `find . -name "name1*"` 

16.Просмотреть содержимое в реальном времени после указанного значения
+ `tail -f name1.txt | grep faucibus` 

17.Отредактировать name1.txt в блокноте и сохранить
посмотреть изменения в терминале
+ `tail -f name1.txt | grep --line-buffered faucibus >> test_log.txt` — с записью в файл
+ `tail -f name1.txt | grep --line-buffered сюда_паттерн >> test_log.txt | tail -f test_log.txt` — с записью в файл и отображением в терминале 

18.Вывести несколько первых строк из текстового файла
+ `head -10 name1.txt` 

19.Вывести несколько последних строк из текстового файла
+ `tail -10 name1.txt` 

20.Просмотреть содержимое длинного файла
+ `less name1.txt`
+ `q` для выхода из режима просмотра 

21.Вывести дату и время
+ `date` 
***
Задание *

22.Отправить http запрос на сервер. http://162.55.220.72:5005/terminal-hw-request
+ curl "http://162.55.220.72:5005/terminal-hw-request" 

Ответ {"Intro":"Hello!! This is your the first response from server","Tasks":{"Task_1":"Send the next URL in terminal: http://162.55.220.72:5005/get_method?name=(set_your_String)&age=(set_your_number)","result":["Your_String","Your_number"]}} 





+ `curl "http://162.55.220.72:5005/get_method?name=(Lyudmila)&age=(38)"` 

вместо (set_your_String) пишем имя вместо (set_your_number) пишем возраст



23.Написать скрипт который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13
`cat > script.sh << EOF
#!/bin/bash
pwd 
mkdir folder_script
cd folder_script
mkdir folder1 folder2 folder3
cd folder3
touch {text4.txt,text5.txt,text6.txt,json3.json,json4.json}
mkdir script_folder1 script_folder2 script_folder3
ls -la
mv text4.txt json3.json script_folder2
mv folder3/{text4.txt,json3.json} folder3/script_folder2
curl "http://162.55.220.72:5005/terminal-hw-request"
curl "http://162.55.220.72:5005/get_method?name=(Lyudmila)&age=(38)"
date 
EOF
Enter
chmod +x script.sh

./script.sh`
