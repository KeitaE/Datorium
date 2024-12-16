# Datorium
uzdevums

public class Car
{
    public int ID { get; set; }
    public string Model { get; set; }
    public decimal HourlyRate { get; set; }
    public decimal KilometerRate { get; set; }
}

public class Client
{
    public int ID { get; set; }
    public string NameSurname { get; set; }
    public string Email { get; set; }
}

public class Rental
{
    public int ID { get; set; }
    public int ClientID { get; set; }
    public int CarID { get; set; }
    public DateTime StartTime { get; set; }
    public DateTime EndTime { get; set; }
    public decimal MileageDriven { get; set; }
    public decimal TotalCost { get; set; }
}

#SQL

CREATE TABLE Cars (
    ID INTEGER PRIMARY KEY AUTOINCREMENT,
    Model TEXT NOT NULL,
    HourlyRate REAL NOT NULL,
    KilometerRate REAL NOT NULL
);

CREATE TABLE Clients (
    ID INTEGER PRIMARY KEY AUTOINCREMENT,
    NameSurname TEXT NOT NULL,
    Email TEXT NOT NULL UNIQUE
);

CREATE TABLE Rentals (
    ID INTEGER PRIMARY KEY AUTOINCREMENT,
    ClientID INTEGER NOT NULL,
    CarID INTEGER NOT NULL,
    StartTime DATETIME NOT NULL,
    EndTime DATETIME,
    MileageDriven REAL,
    TotalCost REAL,
    FOREIGN KEY (ClientID) REFERENCES Clients(ID),
    FOREIGN KEY (CarID) REFERENCES Cars(ID)
);
