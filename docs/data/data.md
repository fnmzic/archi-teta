# Модель предметной области
<!-- Логическая модель, содержащая бизнес-сущности предметной области, атрибуты и связи между ними. 
Подробнее: https://confluence.mts.ru/pages/viewpage.action?pageId=375782602

Используется диаграмма классов UML. Документация: https://plantuml.com/class-diagram 
-->

```plantuml
@startuml
!define ENTITYMODIFIERS


package "helloconf" {
  package Participants {
    class Participant {
      +id: int
      +name: string
      +email: string
      +phone: string
    }
    class Speaker {
      +id: int
      +name: string
      +email: string
      +phone: string
      +company: string
    }
    class Sponsor {
      +id: int
      +name: string
      +email: string
      +phone: string
      +company: string
    }
    class Lessor {
      +id: int
      +name: string
      +email: string
      +phone: string
    }
    class Specialist {
      +id: int
      +name: string
      +email: string
      +phone: string
    }
     class Organizer {
      +id: int
      +name: string
      +email: string
      +phone: string
    }
  }
   

  package Events {
    class Event {
      +id: int
      +name: string
      +description: string
      +start_date: date
      +end_date: date
      +type: string
    }
    class Schedule {
      +id: int
      +event_id: int
      +start_time: time
      +end_time: time
      +location: string
    }
    class Ticket {
      +id: int
      +event_id: int
      +type: string
      +price: float
    }
    class Invitation {
      +id: int
      +event_id: int
      +recipient_id: int
      +sender_id: int
      +message: string
    }
  }


  
  Events.Schedule -- Events.Event : schedule
  Events.Ticket -- Events.Event : ticket
  Events.Invitation -- Events.Event : invitation
  Events.Invitation -- Participants.Speaker : invitee
  Events.Ticket -- Participants.Participant : attendee
  Sponsor --|> Event
  Lessor --|> Event
  Specialist --|> Event
  Organizer -> Event
}
@enduml
```
