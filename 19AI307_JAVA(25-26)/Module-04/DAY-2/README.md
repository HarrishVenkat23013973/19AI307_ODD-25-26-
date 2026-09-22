# Ex.No:4(B)  IMPLEMENT SOLID PRINCIPLES IN JAVA PROGRAM 

## QUESTION:

At an international airport, only one Radar Control Tower exists. This tower is responsible for handling all flight communications regardless of how many flights are coming in. Each incoming flight must contact this tower to register its approach.

To ensure safety and consistency, all flights must communicate with the same instance of the tower. If multiple towers are created, it may lead to inconsistent instructions — a huge risk in aviation.

Your task is to simulate this system using the Singleton pattern.

## AIM:

To simulate an airport radar communication system using the Singleton pattern, ensuring that all incoming flights register through a single shared instance of the RadarControlTower.

## ALGORITHM :

Create a class RadarControlTower with a private static instance variable and private constructor to prevent multiple object creation.

A static getInstance() method that creates the object only once and returns the same instance each time.

A registerFlight() method to store flight names and return the count.

Read the number of incoming flights.

For each flight, read the flight name.

Get the Singleton instance using RadarControlTower.getInstance().

Register the flight and print the updated total.

Ensure every flight interacts with the same RadarControlTower instance.



## PROGRAM:
 ```
/*
Program to implement a SOLID Principles in Java Program
Developed by: HarrishVenkat V
RegisterNumber: 212223240049
*/
```

## SOURCE CODE:


    import java.util.*;
    
    class RadarControlTower {
        private static RadarControlTower instance = null;
        private List<String> flights;
        private RadarControlTower() {
            flights = new ArrayList<>();
        }
        public static RadarControlTower getInstance() {
            if (instance == null) {
                instance = new RadarControlTower();
            }
            return instance;
        }
        public int registerFlight(String flightName) {
            flights.add(flightName);
            return flights.size();
        }
    }
    
    public class prog {
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            int n = sc.nextInt();
            sc.nextLine();
            for (int i = 0; i < n; i++) {
                String flight = sc.nextLine();
                RadarControlTower tower = RadarControlTower.getInstance();
                int total = tower.registerFlight(flight);
                System.out.println(flight + " registered with Radar Control Tower. Total Flights: " + total);
            }
        }
    }




## OUTPUT:

<img width="1126" height="288" alt="image" src="https://github.com/user-attachments/assets/5b14ffb7-d8d8-4e5c-bc67-24cfbee1c7ec" />


## RESULT:
Therefore the program successfully ensures that all flights communicate with a single RadarControlTower instance using the Singleton pattern.

