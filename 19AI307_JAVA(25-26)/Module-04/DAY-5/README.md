# Ex.No:4(D) DESIGN PATTERN  ---- BEHAVIOUR PATTERN

## QUESTION:

Create a ChatRoom class (mediator) and two users (colleagues) who send and receive messages through it. No direct communication allowed.

## AIM:

To Create a ChatRoom class (mediator) and two users (colleagues) who send and receive messages through it. No direct communication allowed.


## ALGORITHM :

Create a ChatRoom class that holds a collection of users, registers users using registerUser(), delivers messages using sendMessage(from, to, message).

Create a User class containing a user name, a reference to the ChatRoom mediator, a send() method that passes messages to the chat room, a receive() method to display incoming messages.

Read two user names and create User objects, automatically registering them with the chat room.

Read the number of chat exchanges.

For each exchange read sender, receiver, and message, call the corresponding user’s send() method.

Ensure all communication happens only through the mediator (ChatRoom), not directly between users.




## PROGRAM:
 ```
/*
Program to implement a Behaviour Pattern using Java
Developed by: HarrishVenkat V
RegisterNumber: 212223240049
*/
```

## SOURCE CODE:


     import java.util.*;
     
     class ChatRoom {
         private Map<String, User> users = new HashMap<>();
     
         public void registerUser(User user) {
             users.put(user.getName(), user);
         }
     
         public void sendMessage(String from, String to, String message) {
             User receiver = users.get(to);
             if (receiver != null) {
                 receiver.receive(from, message);
             } else {
                 System.out.println("User " + to + " not found");
             }
         }
     }
     
     class User {
         private String name;
         private ChatRoom chatRoom;
     
         public User(String name, ChatRoom chatRoom) {
             this.name = name;
             this.chatRoom = chatRoom;
             chatRoom.registerUser(this);
         }
     
         public String getName() {
             return name;
         }
     
         public void send(String to, String message) {
             chatRoom.sendMessage(name, to, message);
         }
     
         public void receive(String from, String message) {
             System.out.println(from + " to " + name + ": " + message);
         }
     }
     
     public class ChatApp {
         public static void main(String[] args) {
             Scanner sc = new Scanner(System.in);
     
             ChatRoom room = new ChatRoom();
             User user1 = new User(sc.nextLine(), room); 
             User user2 = new User(sc.nextLine(), room);
     
             int n = Integer.parseInt(sc.nextLine());
             for (int i = 0; i < n; i++) {
                 String sender = sc.nextLine();
                 String receiver = sc.nextLine();
                 String message = sc.nextLine();
     
                 if (sender.equals(user1.getName())) {
                     user1.send(receiver, message);
                 } else if (sender.equals(user2.getName())) {
                     user2.send(receiver, message);
                 } else {
                     System.out.println("Unknown sender");
                 }
             }
     
             sc.close();
         }
     }




## OUTPUT:

<img width="1107" height="767" alt="image" src="https://github.com/user-attachments/assets/8f7ff282-ddfe-4f71-9d80-512f9c01a1dd" />


## RESULT:
Therefore the program successfully demonstrates message exchange using the Mediator Pattern, with all user communication routed through the ChatRoom.

