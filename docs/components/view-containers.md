```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml
skinparam linetype polyline
skinparam wrapWidth 300
skinparam linetypeComponentSymbol dotted
title helloconf - Диаграмма контейнеров (Витрина событий)
LAYOUT_WITH_LEGEND()
LAYOUT_LANDSCAPE()

System_Boundary(system, "Витрина событий", "") {
  Container(view, "conf-view-srv", "Java, Spring", "Сервис предоставления данных о конференциях")
  Container(reg, "conf-reg-srv", "Java, Spring", "Сервис регистрации на конференции")
  ContainerDb(db, "conf-management-data", "PostgreSQLP", "Хранилище конференций и зарегистрированных участников")
}
@enduml
```
