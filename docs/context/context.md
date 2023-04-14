# Контекст решения
<!-- Окружение системы (роли, участники, внешние системы) и связи системы с ним. Диаграмма контекста C4 и текстовое описание. 
Подробнее: https://confluence.mts.ru/pages/viewpage.action?pageId=375783261
-->
```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

LAYOUT_WITH_LEGEND()

title HELLOCONF C4

Person(user, "Organizers")

System(helloconf, "System") {
  Container(congf, "helloconf", "Web application for managing conference organization") {
    Container(database, "Database", "Database for storing conference information")
    Container(socialmedia, "Social media", "Social media platforms for conference promotion")
    Container(thirdpartyservices, "Third-party services", "Third-party services for conference support")
  }
}

Rel(user, congf, "Uses")
Rel(congf, database, "Reads and writes data to")
Rel(congf, socialmedia, "Promotes conference through")
Rel(congf, thirdpartyservices, "Integrates with")

@enduml
```
