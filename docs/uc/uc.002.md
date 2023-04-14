# UC.002 Редактирование мероприятия
<!-- Подробное описание сценария использования системы с привязкой к ролям участников и задействованным бизнес-сущностям 
https://confluence.mts.ru/pages/viewpage.action?pageId=375782119 
-->
| Название | _Редактирование мероприятия_ |
|:---------------------------|:------|
| Описание | _Сценарий описывает процесс редактирования информации о мероприятии в приложении helloconf, включая изменение названия, даты, времени и описания мероприятия_ |
| Участники | _Организатор мероприятия, оператор приложения_ |
| Триггер | _Организатор мероприятия решил внести изменения в информацию о мероприятии_ |
| Предусловия | _Организатор конференции должен иметь аккаунт в приложении helloconf и иметь достаточные права для редактирования мероприятия_ |
| Постусловия | _Измененная информация о мероприятии сохранена в приложении_ |
| Успешный сценарий | *1) Организатор конференции открывает приложение helloconf и авторизуется               		   2) Организатор мероприятия находит мероприятие, которое нужно отредактировать. 3)Организатор мероприятия выбирает опцию "Редактировать мероприятие". 4)Приложение helloconf отображает форму редактирования мероприятия с текущей информацией о мероприятии. 5)Организатор мероприятия изменяет необходимую информацию, например название, дату, время или описание мероприятия. 6)Организатор мероприятия подтверждает изменения. 7)Приложение KONGF сохраняет измененную информацию о мероприятии и отображает обновленную информацию.*|
| Альтернативный сценарий 1 | *4. Если мероприятие не найдено в приложении helloconf, приложение сообщает об ошибке и предлагает создать новое мероприятие.* |
| Сценарий исключений | *5. Если организатор мероприятия ввел недопустимые данные, например, неверный формат даты или название мероприятия слишком длинное, приложение helloconf сообщает об ошибке и предлагает исправить введенные данные* |
| Требования | *Приложение helloconf должно позволять редактировать информацию о мероприятии FR.005* |