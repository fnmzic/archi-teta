```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml
skinparam linetype polyline
skinparam wrapWidth 200
title helloconf - Диаграмма ограниченных контекстов
LAYOUT_WITH_LEGEND()
LAYOUT_LANDSCAPE()


Person(person, "Организаторы", "Организаторы конференций")
Person(participants, "Участники", "Участники конференций")


System(event, "Система управления событиями", "Обеспечивает добавление, редактирование событий")
System(eventsviews, "Витрина событий", "Отображает конференции")
System_Ext(payment, "Payment Processing", "Handles payment processing for event tickets")
System(reg, "Регистрация", "Регистрация на конференции")

System(notification, "Управление нотификациями", "Обеспечение отправки нотификаций sms/email")
  


Rel_D(person, event, "Создают и редактируют события")
Rel_D(participants, eventsviews, "Просматривают события")
Rel_R(participants, payment, "Оплачивают билеты")
Rel_L(participants, reg, "Регистрируются на события")



Rel_L(event, notification, "Отправляет нотификации об изменениях")
Rel_R(eventsviews, notification, "Отправляет нотификации")


@enduml
```
