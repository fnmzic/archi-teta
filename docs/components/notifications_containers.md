```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

skinparam linetype polyline
skinparam wrapWidth 300
skinparam linetypeComponentSymbol dotted

title helloconf - Диаграмма контейнеров (Управление нотификациями)

LAYOUT_WITH_LEGEND()
LAYOUT_LANDSCAPE()

System_Boundary(system, "Управление нотификациями", "") {
  Container(usn, "user-notify-srv", "Java, Spring", "Сервис управления нотификациями")
  ContainerDb(db, "interactions", "PostgreSQLP", "Хранилище нотификаций")
  ContainerQueue(mq, "mail-queue", "RabbitMQ", "Очередь электронных писем")
  ContainerQueue(sq, "sms-queue", "RabbitMQ", "Очередь sms")
}
Rel_R(usn, mq, "Передает сообщения в канал email рассылки", "HTTP")
Rel_R(usn, sq, "Передает сообщения в канал sms рассылки", "HTTP")
Rel_U(usn, db, "Читает, записывает обращения", "JDBC, SQL")
@enduml
```
