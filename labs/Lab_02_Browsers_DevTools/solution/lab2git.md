### Задание №1. Исследование заголовков и тела обычных запросов и их ответов
*   ##### Что означает каждый из этих заголовков?
```
- Request URL         - запрашиваемый URL, значение хота ресурса.
- Request Method      - GET-запрос используется для получения данных.
- Status Code         - код состояния.
- Remote Address      - удалённый адрес и IP адрес.
- Referrer Policy     - помогает предотвратить утечку данных на сайты, куда идут ссылки.
- content-type        - тип контента запрашиваемой страницы.
- cache-control       - задает инструкции кэширования запросов и ответов.
- cookie              - небольшие данные сохраняемые у пользователя
- user-agent          - часть текствого запроса, в котором информация веб-приложения сообщается сайту.
- referer             - позволяет узнать откуда был отправлен запрос.
```
*  ##### Из каких частей состоит Remote Address? 
Remote address представляет собой строку, состоящую из IP-адреса и порта, разделенных двоеточием. Например, «192.168.0.1:8080». 
*   ##### Что означает порт подключения? 
Порт подключения - это числовой идентификатор, который определяет конкретное приложение или службу на удаленном сервере, с которым клиентское устройство устанавливает соединение. Например, стандартный порт для HTTP - 80. Он важен, потому что он указывает, какому серверному приложению нужно обрабатывать запрос.
*   ##### Какие заголовки повторяются в нескольких секциях? Какой в этом смысл?
Некоторые заголовки, такие как "content-type", могут встречаться как в запросе, так и в ответе. Они служат для указания типа содержимого, который отправляется или ожидается.
*   ##### На какие секции разделены все заголовки? Какой смысл у каждой секции?
Заголовки HTTP-запросов и ответов обычно разделяются на несколько секций, такие как:
```
General: Общая информация о запросе или ответе, включая метод, URL и версию протокола.
Request Headers: Заголовки, отправляемые с запросом, включая User-Agent, Cookie и другие.
Response Headers: Заголовки, возвращаемые в ответе сервера, такие как Content-Type и Cache-Control.
Query String Parameters: Параметры, передаваемые в URL-адресе запроса (для GET-запросов).
Form Data: Данные, отправляемые в теле запроса (для POST-запросов).
Response Body: Тело ответа, содержащее фактические данные или содержимое ресурса, запрошенного клиентом.
Какие заголовки повторяются в нескольких секциях? Какой в этом смысл?
```

*   ##### Что из себя представляет тело ответа?
Тело ответа - это часть HTTP-ответа, которая содержит фактические данные или содержимое ресурса, запрошенного клиентом. Например, в случае веб-страницы, это будет HTML-код страницы. Тело ответа может быть пустым или содержать любой тип данных в зависимости от запроса и ресурса.

### Задание №2. Исследование указывающих ответов сервера

*   ##### Из-за чего произошло изменение адреса в адресной строке? Какие заголовки в этом поучаствовали и как?
Когда сервер возвращает статус ответа 3xx (например, 301 Moved Permanently или 302 Found), это означает, что ресурс был перемещен на другой URL. Заголовки ответа в этом случае могут включать Location, который указывает на новый URL ресурса. Браузер автоматически выполняет перенаправление, следуя этому заголовку, и изменяет адрес в адресной строке соответственно.
*   ##### Адрес был изменён в исходном запросе или потребовались дополнительные запросы, если были дополнительные запросы, то сколько?
В первом запросе было запрошено повышение страницы, во втором запросе мы перешли на полученную страницу.
*   ##### Какой статус ответа имеет первоначальный запрос?
301 Moved Permanently

### Задание №3. Исследование получения и передачи cookie

*   ##### Перечислите название этих параметров и формат данных в них.
```
Названия параметров (Name): Это идентификаторы, используемые для обозначения отдельных куки. Например, "session_id" или "user_token". 
Значения параметров (Value): Значения, связанные с каждым параметром, определяющие содержимое куки. Например, "123456789" или "username=johndoe". 
Другие параметры (Domain, Path, Expires): Эти параметры определяют область действия и срок действия куки. Они не отображаются прямо в заголовках, но их значения могут быть прочитаны из соответствующих атрибутов куки.
``` 
*   ##### Как можно удобно просмотреть все cookie, используемые на странице? Что означают их параметры Name, Value, Domain, Path и Expires?
Для удобного просмотра всех Cookie, используемых на странице, можно воспользоваться инструментами разработчика браузера.
```
Name: Имя cookie параметра.
Value: Значение cookie параметра.
Domain: Домен, на котором cookie параметр может быть использован. Если домен не указан, то cookie параметр может быть использован только на текущем домене.
Path: Путь на сервере, на котором cookie параметр может быть использован. Если путь не указан, то cookie параметр может быть использован на любом пути на сервере.
Expires: Дата и время истечения срока действия cookie
```
* ##### Как просмотреть все cookie связанные с текущим (просматриваемым) сайтом?
В инструментах разработчика, в разделе "Cookies" или "Local Storage", можно фильтровать куки по домену, чтобы просмотреть только те, которые связаны с текущим сайтом.
*   ##### Опишите своими словами как вы понимаете суть и назначение cookie?
Cookie - это текстовый файл, который содержит различную информацию о пользователе и хранится на компьютере для взаимодействия между сайтом и пользователем. Он позволяет сайтам распознавать пользователя и запоминать его язык, аккаунт и предпочтения на сайте, чтобы предоставлять более персонализированный опыт. Однако, некоторые cookie могут использоваться для отслеживания активности пользователя и сбора личной информации, вызывая опасения в отношении конфиденциальности данных.
### Задание №4. Исследование построения документов и сопутствующих запросов
*   ##### Что такое DOM? — Опишите своими словами
DOM-это структура, которая представляет веб-страницу в виде дерева объектов. Она позволяет программистам манипулировать содержимым страницы, изменять ее внешний вид и поведение. DOM позволяет получать доступ к элементам страницы, изменять их свойства и атрибуты, добавлять новые элементы и удалять существующие. Это очень важный инструмент для создания интерактивных веб-сайтов и приложений.
*   ##### Может ли итоговый документ отличаться от тела ответа, полученного от сервера? Если да, то по каким причинам это может происходить?
Да, итоговый документ, который отображается веб-браузером, может отличаться от тела ответа, полученного от сервера.

Это может произойти из-за:

    Обработки на стороне клиента: Веб-браузер может выполнить дополнительные шаги обработки полученного контента перед его отображением.
    Кэширования: Если у браузера есть сохраненная копия страницы в кеше, то он может использовать эту версию вместо повторной загрузки с сервера. В результате, содержимое страницы может быть разным в зависимости от того, когда она была загружена и сохранена в кеше.
    Динамического содержимого: Некоторые части веб-страницы могут быть созданы или изменены с помощью JavaScript или других технологий на стороне клиента.  

* ##### Почему если вы сделали всего один запрос, в списке огромное количество запросов и ответов? Что они из себя представляют и на каком основании браузер их делает?
Даже если сделать всего один запрос в списке будет большое количество запросов и ответов потому, что сеть подгружает всё по частям. Браузер подгружает файлы для получения информации из сети.
Это могут быть различные картинки формата .png, скрипты .script, шрифты font и так далее.

### Задание №5. Определение параметров запроса

* ##### Запрос к какому эндпоинту необходимо выполнить для получения вашего расписания
https://www.rgups.ru/ajax/schedule.php?action=timetable&fac-id=1&course-id=3&group-id=26365&edu-type=internal
* ##### Что содержится в теле ответа
  * таблица с расписанием
  * код
  ```
  <div class="schedule-section">
					<div class="schedule-section-legend"><i></i> – в режиме видеоконференцсвязи</div>
    		
    <table class="table">             <tr>
                <th class="" colspan="6">
                    Понедельник (сегодня)                </th>
            </tr>
                      <tr>
                        <td class="" >1</td>
                        <td class="" >8.20-9.50</td>
                        <td class="" >обе недели</td>
                            <td class="">Военная подготовка ()</td>
                            <td class=""> ..</td>
                            <td class=""></td>
                    </tr>
                      <tr>
                        <td class="" >2</td>
                        <td class="" >10.05-11.35</td>
                        <td class="" >обе недели</td>
                            <td class="">Военная подготовка ()</td>
                            <td class=""> ..</td>
                            <td class=""></td>
                    </tr>
                      <tr>
                        <td class="" >3</td>
                        <td class="" >12.05-13.35</td>
                        <td class="" >обе недели</td>
                            <td class="">Военная подготовка ()</td>
                            <td class=""> ..</td>
                            <td class=""></td>
                    </tr>
                      <tr>
                        <td class="" >4</td>
                        <td class="" >13.50-15.20</td>
                        <td class="" >обе недели</td>
                            <td class="">Военная подготовка ()</td>
                            <td class=""> ..</td>
                            <td class=""></td>
                    </tr>
                      <tr>
                        <td class="" >5</td>
                        <td class="" >15.30-17.00</td>
                        <td class="" >обе недели</td>
                            <td class="">Военная подготовка ()</td>
                            <td class=""> ..</td>
                            <td class=""></td>
                    </tr>

            <tr>
                <th class=" info" colspan="6">
                    Вторник (завтра)                </th>
            </tr>
                      <tr>
                        <td class="success" >2</td>
                        <td class="success" >10.05-11.35</td>
                        <td class="success" >обе недели</td>
                            <td class="success">Системы и технологии искусственного интеллекта (ЛЕК)</td>
                            <td class="success">МОСКАТ Н.А.</td>
                            <td class="success">Д404</td>
                    </tr>
                      <tr>
                        <td class="" >3</td>
                        <td class="" >12.05-13.35</td>
                        <td class="" >обе недели</td>
                            <td class="">Экономика и менеджмент (ПРАК)</td>
                            <td class="">ТИМЧЕНКО О.В.</td>
                            <td class="">С409</td>
                    </tr>
                      <tr>
                        <td class="" >4</td>
                        <td class="" >13.50-15.20</td>
                        <td class="" >обе недели</td>
                            <td class="">Схемотехника и архитектура вычислительных систем (ЛЕК)</td>
                            <td class="">ЛЯЩЕНКО А.М.</td>
                            <td class="">Г313</td>
                    </tr>
                      <tr>
                        <td class="" >5</td>
                        <td class="" >15.30-17.00</td>
                        <td class="" >обе недели</td>
                            <td class="">Системы и технологии искусственного интеллекта (ЛАБ)</td>
                            <td class="">ЖУРАВЛЕВ Д.С. [2]</td>
                            <td class="">Г305</td>
                    </tr>

            <tr>
                <th class="" colspan="6">
                    Среда                </th>
            </tr>
                      <tr>
                        <td class="" >2</td>
                        <td class="" >10.05-11.35</td>
                        <td class="" >обе недели</td>
                            <td class="">Системы и технологии искусственного интеллекта (ЛАБ)</td>
                            <td class="">МОСКАТ Н.А. [1]</td>
                            <td class="">Г305</td>
                    </tr>
    <!--4-->                      <tr>
                        <td class="" rowspan="4">3</td>
                        <td class="" rowspan="4">12.05-13.35</td>
                        <td class="disable " >над чертой</td>
                                  
                                <td class="disable ">Безопасность жизнедеятельности (ЛЕК)</td>
                                <td class="disable ">ПЕРЕВЕРЗЕВ И.Г.</td>
                                <td class="disable ">М150</td>
                        </tr>
                        <tr>
                            <td class=" " rowspan="3">под чертой</td>
                                <td class=" ">Безопасность жизнедеятельности (ЛАБ)</td>
                                <td class=" ">АБДУЛЬМАНОВА К.И. [2]</td>
                                <td class=" ">М158</td>
    </tr><tr>                                <td class=" ">Безопасность жизнедеятельности (ЛАБ)</td>
                                <td class=" ">ЯИЦКОВА Н.М. [1]</td>
                                <td class=" ">М152</td>
    </tr><tr>                          </tr>
                                       </tr>
                      <tr>
                        <td class="" >4</td>
                        <td class="" >13.50-15.20</td>
                        <td class="" >обе недели</td>
                            <td class="">Веб-программирование (ЛЕК)</td>
                            <td class="">КАПКАЕВ А.А.</td>
                            <td class="">Г315</td>
                    </tr>
    <!--5-->                      <tr>
                        <td class="" rowspan="5">5</td>
                        <td class="" rowspan="5">15.30-17.00</td>
                        <td class="disable " rowspan="3">над чертой</td>
                                  
                                <td class="disable ">Веб-программирование (ЛАБ)</td>
                                <td class="disable ">КАПКАЕВ А.А. [1]</td>
                                <td class="disable ">Г302</td>
    </tr><tr>                                  
                                <td class="disable ">Веб-программирование (ЛАБ)</td>
                                <td class="disable ">ХУСАИНОВ В.Р. [2]</td>
                                <td class="disable ">Д412</td>
    </tr><tr>                        </tr>
                        <tr>
                            <td class=" " rowspan="3">под чертой</td>
                                <td class=" ">Веб-программирование (ЛАБ)</td>
                                <td class=" ">КАПКАЕВ А.А. [1]</td>
                                <td class=" ">Г302</td>
    </tr><tr>                                <td class=" ">Веб-программирование (ЛАБ)</td>
                                <td class=" ">ХУСАИНОВ В.Р. [2]</td>
                                <td class=" ">Д406</td>
    </tr><tr>                          </tr>
                                       </tr>
                      <tr>
                        <td class="" rowspan="2">6</td>
                        <td class="" rowspan="2">17.10-18.40</td>
                        <td class="" rowspan="2">обе недели</td>
                            <td class="">Системное программное обеспечение вычислительных систем (ЛАБ)</td>
                            <td class="">НИКИТЧЕНКО С.Л. [2]</td>
                            <td class="">Д406</td>
    </tr><tr>                            <td class="">Системное программное обеспечение вычислительных систем (ЛАБ)</td>
                            <td class="">МИЗЮКОВ Г.С. [1]</td>
                            <td class="">Д407</td>
    </tr><tr>                    </tr>

            <tr>
                <th class="" colspan="6">
                    Четверг                </th>
            </tr>
    <!--4-->                      <tr>
                        <td class="" rowspan="4">1</td>
                        <td class="" rowspan="4">8.20-9.50</td>
                        <td class="disable " rowspan="3">над чертой</td>
                                  
                                <td class="disable ">Схемотехника и архитектура вычислительных систем (ЛАБ)</td>
                                <td class="disable ">МИРОШНИКОВ А.М. [1]</td>
                                <td class="disable ">Г303</td>
    </tr><tr>                                  
                                <td class="disable ">Схемотехника и архитектура вычислительных систем (ЛАБ)</td>
                                <td class="disable ">СОКИРКА А.Д. [2]</td>
                                <td class="disable ">Г302</td>
    </tr><tr>                        </tr>
                        <tr>
                            <td class=" " >под чертой</td>
                                <td class=" ">Безопасность жизнедеятельности (ПРАК)</td>
                                <td class=" ">БАЛАНОВА М.В.</td>
                                <td class=" ">М232</td>
                          </tr>
                                       </tr>
                      <tr>
                        <td class="" >2</td>
                        <td class="" >10.05-11.35</td>
                        <td class="" >обе недели</td>
                            <td class="">Базы данных (ЛЕК)</td>
                            <td class="">ИГНАТЬЕВА О.В.</td>
                            <td class="">Г313</td>
                    </tr>
                      <tr>
                        <td class="" rowspan="2">3</td>
                        <td class="" rowspan="2">12.05-13.35</td>
                        <td class="" rowspan="2">обе недели</td>
                            <td class="">Базы данных (ЛАБ)</td>
                            <td class="">ГАЛЬЦЕВА А.А. [1]</td>
                            <td class="">Г315</td>
    </tr><tr>                            <td class="">Базы данных (ЛАБ)</td>
                            <td class="">МУКОНИНА М.И. [2]</td>
                            <td class="">Г315</td>
    </tr><tr>                    </tr>
            <tr>
                <th class="" colspan="6">
                    Пятница                </th>
            </tr>
                      <tr>
                        <td class="" >2</td>
                        <td class="" >10.05-11.35</td>
                        <td class="" >обе недели</td>
                            <td class="">Экономика и менеджмент (ЛЕК)</td>
                            <td class="">КАЛАШНИКОВ И.А.</td>
                            <td class="">Д404</td>
                    </tr>
                      <tr>
                        <td class="" >3</td>
                        <td class="" >12.05-13.35</td>
                        <td class="" >обе недели</td>
                            <td class="">Системное программное обеспечение вычислительных систем (ЛЕК)</td>
                            <td class="">ЖУКОВ В.В.</td>
                            <td class="">Д404</td>
                    </tr>

    </table></div>
  ```
* ##### Какого типа запрос вы выполнили?
get
* ##### Какие данные вы использовали для получения расписания
```
group-id: 26365 - id группы
action: timetable - Обращение к расписанию
edu-type: internal - тип обучения 
course-id: 3 # - id курса
fac-id: 1 - id факультета

```