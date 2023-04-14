# UC.005 Создание расписания
<!-- Подробное описание сценария использования системы с привязкой к ролям участников и задействованным бизнес-сущностям 
https://confluence.mts.ru/pages/viewpage.action?pageId=375782119 
-->
| Название | _Создание расписания_ |
|:---------------------------|:------|
| Описание | _Сценарий использования для создания расписания в приложении позволяет пользователю создавать и настраивать расписание мероприятий_ |
| Участники | _Пользователь приложения_ |
| Триггер | _Пользователь запускает приложение и выбирает опцию "Создать расписание"._ |
| Предусловия | _Пользователь должен иметь установленное приложение hellocnf на своем устройстве и быть авторизованным в приложении_ |
| Постусловия | _Создано новое расписание в приложении_ |
| Успешный сценарий | *1) Пользователь заходит в раздел "Расписание" 2) Пользователь выбирает опцию "Создать расписание". 3)Пользователь указывает название расписания и описание. 4)Пользователь выбирает периодичность и даты проведения мероприятий. 5) Пользователь выбирает место проведения мероприятий. 6) Пользователь настраивает параметры расписания, такие как время начала и конца мероприятий, продолжительность. 7)Пользователь сохраняет расписание.*|
| Альтернативный сценарий 1 | *3а. Пользователь не указывает название или описание расписания. Приложение выводит сообщение об ошибке и предлагает указать недостающие данные. 4а. Пользователь выбирает неправильные даты проведения мероприятий. Приложение выводит сообщение об ошибке и предлагает выбрать корректные даты.* |
| Сценарий исключений | *5a. Не удалось выбрать место проведения мероприятий. Приложение выводит сообщение об ошибке и предлагает повторить попытку позже. 7a. Не удалось сохранить расписание. Приложение выводит сообщение об ошибке и предлагает повторить попытку позже.* |
| Требования | *_Система должна обеспечивать возможность создавать расписание мероприятия с указанием времени начала и конца, места проведения_ FR.002* |