Для возможности использования PostgreSQL в качестве СУБД для 1С:Предприятие, необходимо скачать и установить следующий набор драйверов или просто можно скачать со стороннего сайта:  (https://drive.google.com/file/d/1vE9PRcJjXYNGdw97mTkQ5rJGkKV3gdAb/view?usp=drive_link)
 
<img width="734" height="450" alt="image" src="https://github.com/user-attachments/assets/2a6084d1-c6b6-466e-a364-d0699fa62fec" />

Рисунок 1 - Установочное окно



Далее устанавливаем драйвер (рисунок 2).

 <img width="760" height="469" alt="image" src="https://github.com/user-attachments/assets/46428eea-9b4f-45a0-a90f-661ccba177d7" />

Рисунок 2 - Установка



Установка производится стандартно (step-by-step).

Далее необходимой перейти в приложение «ODBC Data Sources (32-bit)» как показано на рисунке 3.

 <img width="599" height="526" alt="image" src="https://github.com/user-attachments/assets/97480178-0327-439d-b3a9-6ce7377fdc14" />

Рисунок 3 - Переход в приложение


В части «Пользовательский DNS» необходимо нажать на кнопку «Добавить» и настроить подключение к базе данных (рисунок 4).

 <img width="679" height="498" alt="image" src="https://github.com/user-attachments/assets/a25a7b54-fc6d-4cea-9d3c-102983c314d0" />

Рисунок 4 - Добавление подключения к БД
	
  Далее нужно выбрать драйвер «PostgreSQL Unicode», как на рисунке 5.
  
 <img width="720" height="535" alt="image" src="https://github.com/user-attachments/assets/f6701c23-ea80-4b03-9ff1-4d4cc2945f73" />

Рисунок 5 - Добавление драйвера


Дальше создаем саму базу (желательно указать данные БД, которая уже была ранее создана в PostgreSQL).

Также важно, если порт не подходит, нужно попробовать (5432 или 5434).

 <img width="766" height="456" alt="image" src="https://github.com/user-attachments/assets/b37984c6-4a5a-4663-be46-7616a25d4d8a" />

Рисунок 6 - Создание подключения к существующей БД

<img width="757" height="564" alt="image" src="https://github.com/user-attachments/assets/085a119d-e901-4ef1-b27e-745e0e80c18d" />
 
Рисунок 7 - Итоговый вид подключения


После удачного подключения, переходим в 1С: Предприятие, создаем новую информационную систему и в дереве конфигурации данной системе создадим «Внешние источники данных».

 <img width="761" height="559" alt="image" src="https://github.com/user-attachments/assets/0949d538-b8f0-4f51-b23a-c9308c7912c5" />

Рисунок 8 - Дерево конфигурации


Для внешнего источника данных зададим имя: PostgreSQL и выберем режим управления блокировкой данных: Автоматический (рисунок 9).

 <img width="603" height="582" alt="image" src="https://github.com/user-attachments/assets/603f4661-7603-4744-81bb-3b615e66dd5f" />

Рисунок 9 - Создание внешнего источника данных


На вкладке «Данные» добавим новую таблицу с параметром «Выбрать из списка таблиц внешнего источника данных….» (рисунок 10).

 <img width="636" height="336" alt="image" src="https://github.com/user-attachments/assets/f13bf329-501e-4fdd-9d6a-22f6c646e0e7" />

Рисунок 10 - Добавление новой таблицы

 <img width="840" height="444" alt="image" src="https://github.com/user-attachments/assets/af0dcd27-cb9d-438c-8abe-9d348a00d290" />

Рисунок 11 - Настройка внешнего источника данных


После выбора появится окно, в котором необходимо в строке соединения прописать параметры соединения, которые представлены на рисунке 12.

 <img width="842" height="413" alt="image" src="https://github.com/user-attachments/assets/b693e2be-149c-4920-9d76-f164b2ca0785" />

Рисунок 12 - Параметры соединения
 
  
  Код строки соединения представлен ниже: 
  
Driver={PostgreSQL Unicode};Server=localhost;Port=5434;Database=Zoopark;Uid=postgres;Pwd=123;STMT=utf8

Далее необходимо выбирать нужные нам таблицы для соединения. В данном окне перечень таблиц по вашей БД будут отличаться от представленных (рисунок 13).

 <img width="846" height="453" alt="image" src="https://github.com/user-attachments/assets/cd5a99d6-4015-4d2b-abed-88cea42cbd13" />

Рисунок 13 - Выбор таблиц для внешнего соединения


В результате выбора таблиц будут отображены во внешнем источнике.

 <img width="641" height="611" alt="image" src="https://github.com/user-attachments/assets/afc9862d-0d8f-4d82-93ef-a97db7f43426" />

Рисунок 14. Добавление таблиц


После добавления таблиц во внешних источниках сохраняем конфигурацию и запускаем 1С: Предприятие (рисунок 15).

 <img width="869" height="130" alt="image" src="https://github.com/user-attachments/assets/145bbf2c-c298-4372-b816-940d2a66b8a5" />

Рисунок 15 - Конфигурация 1С:Предприятие


Далее необходимо перейти в таблицу и подтвердить подключение по параметрам подключения (рисунок 16).

 <img width="803" height="443" alt="image" src="https://github.com/user-attachments/assets/8962b42c-4266-4b72-8ffe-b481edb79f4d" />

Рисунок 16 - Параметры подключения


Далее вводим имя пользователя и пароль от СУБД PostgreSQL.

 <img width="707" height="204" alt="image" src="https://github.com/user-attachments/assets/ba7125f5-fcc3-4621-99e2-e5d470aeb741" />

Рисунок 17 - Авторизация
	
  
  После авторизации появится сообщение о том, что соединение с внешним источником данных выполнено.
  
 <img width="488" height="142" alt="image" src="https://github.com/user-attachments/assets/5e6abe18-eb5d-4887-ab66-b23513edaadd" />

Рисунок 18 - Соединение выполнено


После подключения необходимо нажать F5, и далее заполнить таблицы данными (рисунок 19).

 <img width="850" height="472" alt="image" src="https://github.com/user-attachments/assets/3e377fe1-3b6e-436f-b136-5af60528a9f6" />

Рисунок 19 - Конечный перенос БД
