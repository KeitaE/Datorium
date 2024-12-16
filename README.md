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
