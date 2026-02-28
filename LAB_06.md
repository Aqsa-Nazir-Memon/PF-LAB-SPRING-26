## 1. Student Attendance Counter (For Loop – Known Iterations)
```c
#include <stdio.h>
int main()
{
    int status, present=0;
    for(int i=1; i<=30; i++){
        printf("Enter Attendence of Student: %d (1= Present, 0= Absent): " , i);
        scanf("%d", &status);
        if (status==1){
            present++;
        }
    }
    printf("Total Students Present: %d", present);
    
    return 0;
}
```
## 2. ATM Withdrawal System (While Loop – Condition Based)
```c
#include <stdio.h>
int main()
{
    float balance, withdraw;
    printf ("Enter Initial Amount :");
    scanf("%f", &balance);
    while(balance>0){
        printf("Enter Withdraw Amount: ");
        scanf("%f", &withdraw);
        balance = balance - withdraw;
        printf("Remaining Balance: %2f\n", balance);
    }
    printf("Balance Exhausted !");
    return 0;
}
```
## 3.Password Retry System (Do-While Loop – At Least One Execution)
```c
#include <stdio.h> 
int main(){
    int password;
    do{
    printf("Enter Password:");
    scanf("%d", &password);
    if(password!=1234){
        printf("Incorect Password! Try Again!\n");
    }
}
    while(password != 1234);
    printf("Access Granted !");
    
    return 0;
    
}
```
## 4. Sum of First N Natural Numbers (For Loop)
```c
#include <stdio.h> 
int main(){
    int N, sum=0;
    printf ("Enter a Number : ");
    scanf("%d", &N);
    for(int i = 1; i <=N; i++){
    sum += i;
    }
    printf ("Sum of First %d natural numbers = %d\n", N , sum);
    return 0;
    
}
```
## 5. Temperature Monitoring System (While Loop – Dynamic Input Handling)
```c
#include <stdio.h>
int main() {
    float temp, sum = 0, average;
    int count = 0;

    while (1) {
        printf("Enter temperature (-999 to stop): ");
        scanf("%f", &temp);

        if (temp == -999)
            break;
        sum = sum + temp;
        count = count + 1;
    }
    if (count > 0) {
        average = sum / count;
        printf("Average Temperature = %.2f\n", average);
    } else {
        printf("No valid temperature readings entered.\n");
    }

    return 0;
}
```
## 6. Multiplication Table Generator (For Loop – Controlled Iterations)
```c
#include <stdio.h>
int main() {
    int num, i;
    printf("Enter a number: ");
    scanf("%d", &num);

    printf("Multiplication Table of %d:\n", num);

    for (i = 1; i <= 10; i++) {
        printf("%d x %d = %d\n", num, i, num * i);
    }
    return 0;
}
```
## 7. Menu-Driven Calculator (Do-While Loop – Exit Controlled Loop)
```c
#include <stdio.h>
int main() {
    int choice;
    float num1, num2, result;
    do {
        printf("\n   Simple Calculator   \n");
        printf("1. Addition\n");
        printf("2. Subtraction\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        if (choice == 1) {
            printf("Enter two numbers: ");
            scanf("%f %f", &num1, &num2);
            result = num1+num2;
            printf("Result = %.2f\n", result);
        }
        else if (choice == 2){
            printf("Enter two numbers: ");
            scanf("%f %f", &num1, &num2);
            result = num1-num2;
            printf("Result = %.2f\n", result);
        }
        else if (choice== 3) {
            printf("Exiting program...\n");
        }
        else {
            printf("Invalid choice! \n");
        }
    } while (choice != 3);
    return 0;
}
```
## 8. Number Guessing Game (While Loop – Control Flow Management)
```c
#include <stdio.h>

int main() {
    int guess;
    int correctNumber = 7;

    printf("Number Guessing Game\n");
    printf("Enter your guess: ");
    scanf("%d", &guess);

    while (guess != correctNumber) {

        if (guess > correctNumber) {
            printf("Too High!\n");
        } 
        else {
            printf("Too Low!\n");
        }
        printf("Try again: ");
        scanf("%d", &guess);
    }
    printf("Correct!\n");
    return 0;
}
```
## 9. Factory Production Planning System (For Loop – Logical Iteration &amp; Multiplicative Growth)
```c
#include <stdio.h>
int main() {
    int N, i;
    int total = 0;

    printf("Enter number of boxes: ");
    scanf("%d", &N);

    for (i = 1; i <= N; i++) {
        total = total + i;   
    }
    printf("Total decorative items required = %d\n", total);
    return 0;
}
```
## 10. University Data Analysis System (While Loop – Logical Classification &amp; Sentinel Control)
```c
#include <stdio.h>
int main() {
    int score;
    int distinction =0, pass= 0, fail= 0;
    int student=1;

    printf("Enter student scores (0–100).\n");
    printf("Enter -1 to stop.\n");
       while (1) {
        printf("Enter score for student %d: ", student);
        scanf("%d", &score);

        if (score == -1) {
            break;
        }
        if (score >= 75 && score <= 100) {
            distinction++;
        }
        else if (score >= 50 && score <= 74) {
            pass++;
        }
        else if (score >= 0 && score < 50) {
            fail++;
        }
        else {
            printf("Invalid score! Please enter a score between 0 and 100.\n");
            continue; 
        }
        student++;
    }
    printf("\n  Result \n");
    printf("Distinction: %d\n", distinction);
    printf("Pass: %d\n", pass);
    printf("Fail: %d\n", fail);
    return 0;
}
```
## 11. Online Shopping Cart Checkout System (Do-While Loop – Exit Controlled &amp; User Choice Based)
```c
#include <stdio.h>
int main() {
    float price, total = 0, finalAmount;
    int choice;

    printf("Online Shopping Cart Checkout System \n");
    do {
        printf("Enter price of product: ");
        scanf("%f", &price);

        if (price < 0) {
            printf("Invalid price! Please enter a positive value.\n");
            continue; 
        }
        total += price;

        printf("Do you want to add another product? (1 = Yes, 0 = No): ");
        scanf("%d", &choice);

    } while (choice == 1);

    if (total > 5000) {
        finalAmount = total * 0.95;
        printf("Total bill: %.2f\n", total);
        printf("Discount applied (5%%). Final Amount: %.2f\n", finalAmount);
    } else {
        finalAmount = total;
        printf("Final Amount: %.2f\n", finalAmount);
    }
    printf("Thank you for shopping! \n");

    return 0;
}
```
## 12. Bus Seat Reservation Monitoring System (While Loop – Conditional Termination &amp; Logical Control)
```c
#include <stdio.h>
int main() {
    int totalSeats = 40;
    int bookedSeats = 0;
    int choice;

    printf("Bus Seat Reservation System\n");
    printf("Enter (1) to book a seat, (0) to stop !\n ");
    
    while (bookedSeats < totalSeats) {
        printf("\nEnter Choice: ");
        scanf("%d", &choice);

        if (choice == 0) {
            printf("Booking stopped by operator.\n");
            break; 
        } 
        else if (choice == 1) {
            bookedSeats++;
            printf("Seat booked successfully. Remaining seats: %d\n", totalSeats - bookedSeats);
        } 
        else {
            printf("Invalid choice! Please enter 1 or 0.\n");
        }
    }
    if (bookedSeats == totalSeats) {
        printf("\nAll seats are booked. No seats available.\n");
    }
    printf("Total seats booked: %d\n", bookedSeats);
    printf("Remaining seats: %d\n", totalSeats - bookedSeats);

    return 0;
}
```
