# java-Project
import java.util.Scanner;

public class CarManagement {

    public static void main(String[] args) {
        CarDealer carDealer = new CarDealer();
        System.out.println(carDealer.displayDealer);

        Scanner scanner = new Scanner(System.in);
        Car[] cars = initializeCars(); // Initialize predefined car details

        System.out.println("Car details:");
        for (int i = 0; i < cars.length; i++) {
            System.out.println((i + 1) + ". " + cars[i].getName());
        }

        // Selecting a car and displaying its details
        System.out.println("\nEnter the number of the car you want to view:");
        int index = scanner.nextInt();
        if (index >= 1 && index <= cars.length) {
            System.out.println("Details of selected car:");
            switch (index) {
                case 1:
                    System.out.println(cars[0].getDetail());
                    break;
                case 2:
                    System.out.println(cars[1].getDetail());
                    break;
                case 3:
                    System.out.println(cars[2].getDetail());
                    break;
                case 4:
                    System.out.println(cars[3].getDetail());
                    break;
                case 5:
                    System.out.println(cars[4].getDetail());
                    break;
                // Add more cases for additional cars if needed
                default:
                    System.out.println("Invalid number");
            }

        } else {
            System.out.println("Invalid number");
        }

        scanner.close();
    }

    // Method to initialize predefined car details
    private static Car[] initializeCars() {
        return new Car[]{
                new Car("Toyota Camry", 25000, 2020, "Silver", 20000),
                new Car("Ford Mustang", 30000, 2018, "Red", 30000),
                new Car("Honda Civic", 20000, 2019, "Blue", 15000),
                new Car("Chevrolet Silverado", 35000, 2017, "Black", 40000),
                new Car("BMW X5", 50000, 2021, "White", 10000)
        };
    }
}

class Car {
    private String name;
    private double price;
    private int year;
    private String color;
    private int miles;

    public Car(String name, double price, int year, String color, int miles) {
        this.name = name;
        this.price = price;
        this.year = year;
        this.color = color;
        this.miles = miles;
    }

    public String getName() {
        return name;
    }

    public double getPrice() {
        return price;
    }

    public int getYear() {
        return year;
    }

    public String getColor() {
        return color;
    }

    public int getMiles() {
        return miles;
    }

    public String getDetail() {
        return "\n\nCar Name: " + name + ",\nPrice:$" +price + ", \nYear: " + year + ", \nColor: " + color + ", \nMiles: " + miles;
    }
}

// New class added
class CarDealer {
    // Instantiation of CarDealer object
    String displayDealer = "Welcome to our car dealership! . " +
            "\nWe have a wide range of cars available for you. " +
            "\nFeel free to browse through our collection. ";

}
