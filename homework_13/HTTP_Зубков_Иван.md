Дай определение терминам:
	•	HTTP (Hyper Text Transfer Protocol) отвечает за обмен данными между клиентом и сервером, используя модель “запрос - ответ”. Используется для загрузки страниц, картинок и прочего. 
	•	HTTPS — это тоже самое что и HTTP, но с дополнительным шифрованием для безопасности, работающее поверх TLS/SSL. 
	•	Клиент-серверная модель — это схема взаимодействия, где клиент инициирует запрос, а сервер обрабатывает запрос и возвращает ответ.
	•	Идемпотентность — свойство операции, которое означает, что при повторении операции она дает такой же результат, что и при выполнении одной операции. 

2.1. Разбери запрос
Дан HTTP-запрос:
http
POST /api/users HTTP/1.1
Host: example.com
Content-Type: application/json
Authorization: Bearer eyJhbGciOiJIUzI1NiIs...
Content-Length: 58

{"name": "Иван", "email": "ivan@mail.com"}
Ответь на вопросы:
	•	Какой метод используется? POST
	•	Какой путь (endpoint) запрашивается? /api/users
	•	Какая версия HTTP? HTTP/1.1
	•	Что означает заголовок Content-Type? Указывает формат тела запроса, здесь значит, что тело запроса передается в формате JSON.
	•	Что означает заголовок Authorization? Это заголовок авторизации. Здесь передается токен доступа для аутентификации клиента. 
	•	Где находится тело запроса? В фигурных скобках или в JSON файле. 
Дан HTTP-ответ:
http
HTTP/1.1 201 Created
Content-Type: application/json
Location: /api/users/42

{"id": 42, "name": "Иван", "email": "ivan@mail.com"}
Ответить:
	•	Что означает статус-код 201? 201 означает, что запрос прошел успешно и в итоге был создан новый ресурс. 
	•	Зачем нужен заголовок Location? Указывает адрес только что созданного нового ресурса. 
	•	Что находится в теле ответа? В теле ответа находятся данные нового созданного ресурса в формате JSON. 
2.3. Собери запрос сам
Составь HTTP-запрос для:
	•	Получения списка всех товаровhttpGET /api/products HTTP/1.1Host: example.comAuthorization: Bearer eyJhbGciOiJIUzI1NiIs…Accept: application/json
	•	Создания нового товара с именем "Ноутбук" и ценой 50000httpPOST /api/products HTTP/1.1Host: example.comContent-Type: application/jsonAuthorization: Bearer eyJhbGciOiJIUzI1NiIs…
{"name": "Ноутбук", "price": 50000}
	•	Удаления товара с id=7httpDELETE /api/products/7 HTTP/1.1Host: example.comAuthorization: Bearer eyJhbGciOiJIUzI1NiIs…
	•	Обновления товара с id=3 (изменить цену на 45000)httpPUT /api/products/3 HTTP/1.1Host: example.comContent-Type: application/jsonAuthorization: Bearer eyJhbGciOiJIUzI1NiIs…
{"price": 45000}

Зубков Иван