#include <iostream>   
using namespace std;  
int main() {

    int rooms[10];            
    int foodOrder[10];        

    for (int i = 0; i < 10; i++) {
        rooms[i] = 0;         
        foodOrder[i] = 0;     
    }
    int choice = 0;  

    do {
        
        cout << "\nMenu:\n";
        cout << "1. Display Available Rooms\n"; 
        cout << "2. Book a Room\n";             
        cout << "3. Checkout from a Room\n";    
        cout << "4. Order Food\n";              
        cout << "5. Exit\n";                    
        cout << "Enter your choice: ";
        cin >> choice;  

        if (choice == 1) {
        
            cout << "\nDisplaying all available rooms:\n";
            bool availableRoomFound = false;

            for (int i = 0; i < 10; i++) {
                if (rooms[i] == 0) {
                    cout << "Room " << i + 1 << " is available.\n";
                    availableRoomFound = true;
                }
            }

            if (!availableRoomFound) {
                cout << "No rooms are currently available.\n";
            }

        } else if (choice == 2) {
            
            cout << "\nBooking a room:\n";
            cout << "Enter the room number you want to book (1-10): ";
            int roomNumber;
            cin >> roomNumber;

            if (roomNumber < 1 || roomNumber > 10) {
                cout << "Invalid room number! Please enter a number between 1 and 10.\n";
            } else if (rooms[roomNumber - 1] == 1) {
                cout << "Room " << roomNumber << " is already booked.\n";
            } else {
                rooms[roomNumber - 1] = 1;
                cout << "Room " << roomNumber << " has been successfully booked.\n";
            }

        } else if (choice == 3) {
            
            cout << "\nCheckout from a room:\n";
            cout << "Enter the room number you want to checkout (1-10): ";
            int roomNumber;
            cin >> roomNumber;



            

            if (roomNumber < 1 || roomNumber > 10) {
                cout << "Invalid room number! Please enter a number between 1 and 10.\n";
            } else if (rooms[roomNumber - 1] == 0) {
                cout << "Room " << roomNumber << " is already available.\n";
            } else {
                rooms[roomNumber - 1] = 0;
                foodOrder[roomNumber - 1] = 0;  
                cout << "Room " << roomNumber << " has been successfully checked out.\n";
            }

        } else if (choice == 4) {
            
            cout << "\nOrdering food:\n";
            cout << "Enter the room number you want to order food for (1-10): ";
            int roomNumber;
            cin >> roomNumber;

            if (roomNumber < 1 || roomNumber > 10) {
                cout << "Invalid room number! Please enter a number between 1 and 10.\n";
            } else if (rooms[roomNumber - 1] == 0) {
                cout << "Room " << roomNumber << " is not booked. Please book the room first.\n";
            } else if (foodOrder[roomNumber - 1] == 1) {
                cout << "Food has already been ordered for Room " << roomNumber << ".\n";
            } else {
                
                cout << "Select food option:\n";
                cout << "1. Pizza\n";
                cout << "2. Burger\n";
                cout << "3. Pasta\n";
                cout << "4. Salad\n";
                cout << "5. Sandwich\n";
                cout << "6. Noodles\n";
                cout << "7. Soup\n";
                cout << "8. Fried Rice\n";
                cout << "9. Ice Cream\n";
                cout << "10. Coffee\n";
                cout << "Enter your food choice: ";
                int foodChoice;
                cin >> foodChoice;

                
                if (foodChoice < 1 || foodChoice > 10) {
                    cout << "Invalid food choice! Please select a valid option.\n";
                } else {
                    foodOrder[roomNumber - 1] = 1;  
                    cout << "Food has been ordered for Room " << roomNumber << ".\n";
                }
            }

        } else if (choice == 5) {
            
            cout << "Exiting the program. Thank you for using the Hotel Management System!\n";
        } else {
            cout << "Invalid choice! Please select a valid option from the menu.\n";
        }

    } while (choice != 5);  

    return 0;  
}
