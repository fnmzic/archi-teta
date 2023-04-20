@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

LAYOUT_WITH_LEGEND()

title helloconf - Container Diagram

Person(user, "User")

System_Boundary(kongf, "helloconf") {
  Container(web, "Core helloconf", "Allows users to create and manage events")
  ContainerDb(database, "Database", "Stores event and user data", "Yellow")
  Container(email, "Email Service", "Sends email notifications to users")
  Container(payment, "Payment Gateway", "Processes event payment transactions")
  Container(sms, "SMS Service", "Sends SMS notifications to users")
  ContainerDb(imagestore, "Image Storage", "Stores images for events")
  Container(usn, "User Notifications Service", "Sends notifications to channels")
  Container(queueMail, "Queue for mails", "AMPQ")
  Container(queueSMS, "Ques for sms", "AMPQ")
}

Rel(user, web, "Uses")

Rel(web, database, "Reads from and writes to", "JDBC, SQL")
Rel(web, usn, "Sends notifications", "HTTP")
Rel(queueMail, email, "Sends notifications", "")
Rel(web, payment, "Processes payments using", "HTTP")
Rel(queueSMS, sms, "Sends notifications using", "AMPQ")
Rel(web, imagestore, "Stores images using", "HTTP")

Rel(usn, queueMail, "Sends notifications using", "AMPQ")
Rel(usn, queueSMS, "Sends notifications using", "AMPQ")

@enduml
