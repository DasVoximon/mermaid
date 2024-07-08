erDiagram
    Member { MemberID(PK) ; Name ; AgeGroup ; Stream ; ContactInfo }
    Program { ProgramID(PK) ; Title ; Topic ; Description ; AgeGroup ; Stream }
    Course { CourseID(PK) ; Title ; Description ; StartDate ; EndDate ; ProgramID(FK) }
    Event { EventID(PK) ; Type ; Description ; Date ; RoomID(FK) }
    Room { RoomID(PK) ; FloorNumber ; Type }
    ResourcePerson { ResourcePersonID(PK) ; Name ; Expertise }
    Registration { RegistrationID(PK) ; MemberID(FK) ; CourseID(FK) }

    MEMBER RELATES REGISTERS_FOR(Many-to-Many) COURSE
    PROGRAM -| HAS_COURSES(One-to-Many) COURSE
    COURSE -| HAS_RESOURCE_PERSON(One-to-Many) RESOURCEPERSON
    EVENT -| USES(One-to-Many) ROOM
    ROOM || HOLDS(One-to-Many) EVENT
    
