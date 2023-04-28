```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml
skinparam linetype polyline
skinparam wrapWidth 300
skinparam linetypeComponentSymbol dotted
title helloconf - Диаграмма контейнеров (Система управления событиями)
LAYOUT_WITH_LEGEND()
LAYOUT_LANDSCAPE()

System(system, "Система управления событиями", "") {
  Container(auth, "auth-app-srv", "Java, Spring Security", "Сервисы аутентификации запросов")
  Container(events, "conf-management-srv", "Java, Spring Boot", "Управление конференциями и мероприятиями")
  Container(db, "conf-management-data", "PostgreSQLP", "Хранилище конференций и мероприятий")
  Container(dbimages, "conf-management-images", "MongoDB", "Хранилище картинок для мероприятий")
}
@enduml
```
