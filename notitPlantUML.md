@startuml
hide footbox
participant "Client" as A
participant "Sever" as B

A -> B : {"Noti03"}
B --> A :{"Noti01", "Noti02", "Noti03"}
A --> A : result 
note left:Client ไม่สนใจ message นี้ \nและถือว่าจบการทำงานทั้งหมด
footer รูปที่ 1 Sever ส่งรหัส Noti ที่เก่ากว่า client
@enduml

@startuml
hide footbox
footer รูปที่ 2 Sever ส่งรหัส Noti ต่อจากที่ client มีอยู่

Client -> Sever : [{"Noti01"}]
Sever --> Client : [{"Noti02", "Noti03", "Noti04"}]
Client --> Client : result 
rnote over Client
 กล่อง 1
 - - - - - - - -
[{
    "Noti02", 
    "Noti03", 
    "Noti04"
}]
endrnote
@enduml

@startuml
hide footbox
participant "Client" as A
participant "Sever" as B

A -> B : {"Noti01"}
B --> A :{"Noti04", "Noti05", "Noti06"}
A --> A : result 
note left:Client Sync noti จาก Sever ใหม่
footer รูปที่ 3 Sever ส่งรหัส Noti ไม่ต่อจากที่ client มีอยู่
@enduml
