# base-de-datos
=====================================================

Primer repositorio en github

=====================================================

Tarea cuarentena-Natalia Bilbao Cano-Codigo 40987

=====================================================




create table Persona(

    CI int not null,
    
    nombres varchar(30),
    
    apellidos varchar(30),
    
    fechaNacimiento DATETIME,
    
    PRIMARY KEY (CI)
    
);




reate table Especialidad(

    ID int not null AUTO_INCREMENT,
    
    nombre varchar(30),
    
    PRIMARY KEY (ID)
    
);




create table Consultorio(

    ID int not null AUTO_INCREMENT,
    
    piso int not null,
    
    nro int not null,
    
    PRIMARY KEY (ID)
    
);




CREATE TABLE Paciente (
    
    ID int NOT NULL AUTO_INCREMENT,
    
    PersonaID int,
    
    PRIMARY KEY (ID),
    
    FOREIGN KEY (PersonaID) REFERENCES Persona(CI)

);




CREATE TABLE Doctor (
    
    ID int NOT NULL AUTO_INCREMENT,
    
    ConsultorioID int,
    
    EspecialidadID int,
    
    PersonaID int,
    
    PRIMARY KEY (ID),
    
    FOREIGN KEY (ConsultorioID) REFERENCES Consultorio(ID),
    
    FOREIGN KEY (EspecialidadID) REFERENCES Especialidad(ID),
    
    FOREIGN KEY (PersonaID) REFERENCES Persona(CI)

);





CREATE TABLE Consulta (
    
    PacienteID int,
    
    DoctorID int,
    
    fecha DATETIME, 
    
    FOREIGN KEY (PacienteID) REFERENCES Paciente(ID),
    
    FOREIGN KEY (DoctorID) REFERENCES Doctor(ID),
    
    CONSTRAINT PK_Consulta PRIMARY KEY (PacienteID,DoctorID)

);



=======================================================================

Insertar Registros

=======================================================================

INSERT INTO Persona (CI, nombres, apellidos, fechaNacimiento)

VALUES (8301163, 'Paul', 'Landaeta Flores', '1991-03-25');

INSERT INTO Persona (CI, nombres, apellidos, fechaNacimiento)

VALUES (4923051, 'Julio Jesus', 'Herrera Quintanilla', '1995-04-04');

INSERT INTO Persona (CI, nombres, apellidos, fechaNacimiento)

VALUES (10935516, 'Cristoffer', 'Mollinedo Velasco', '1994-09-12');

INSERT INTO Persona (CI, nombres, apellidos, fechaNacimiento)

VALUES (12452751, 'Aldo Enrique', 'Monzon Quisbert', '1994-04-05');

INSERT INTO Persona (CI, nombres, apellidos, fechaNacimiento)

VALUES (10935512, 'Alexander', 'Mollinedo Velasco', '2000-04-12');

INSERT INTO Especialidad 

VALUES (0,'oftalmologia');

INSERT INTO Especialidad 

VALUES (0,'pediatria');

INSERT INTO Especialidad 

VALUES (0,'dermatologia');

INSERT INTO Especialidad 

VALUES (0,'cardeologia');

INSERT INTO Especialidad 

VALUES (0,'ginecologia');

insert into Consultorio 

values (0, 1,104), 
       
       (0, 1,103),
       
       (0, 1,102),
       
       (0, 1,101),
       
       (0, 1,100);
