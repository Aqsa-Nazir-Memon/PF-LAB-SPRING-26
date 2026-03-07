### 1) Write a C program that takes 5 integers in an array and shifts all elements one position to the right, and moves the last element to the first position.
```c
#include <stdio.h>
int main() {
    int arr[5];
    int i, last;
    printf("Enter 5 Numbers: ");
        for(i = 0; i < 5; i++) {
            scanf("%d", &arr[i]);
    }
    last = arr[4];
        for(i = 4; i > 0; i--) {
            arr[i] = arr[i - 1];
    }
    arr[0] = last;
        printf("Output: ");
        for(i = 0; i < 5; i++) {
            printf("%d ", arr[i]);
    }
    return 0;
}
```
### 2) Write a program that reads the 10 numbers from user and store these numbers into an array of same size. You program should provide a searching mechanism in such a way that how many times a particular number occurred and then print it on screen. If number is not in array, then program should display a message “number not found”.
```c
#include <stdio.h>
int main() 
{
    int arr[10];
    int i, num;
    int count = 0;

    printf("Enter 10 Numbers:\n");
    for(i = 0; i < 10; i++) {
        scanf("%d", &arr[i]);
    }
    printf("Enter number to search: ");
    scanf("%d", &num);
    
    for(i = 0; i < 10; i++) {
        if(arr[i] == num) {
            count++;
        }
    }
    if(count > 0) {
        printf("Number %d occurred %d times.\n", num, count);
    } 
    else{
        printf("Number not found.\n");
    }
    return 0;
}
```
### 3) Sir. Talha Shahid ask you to write you a program which can help him in storing your quiz marks for pass students within range [5-10] will be stored, consider there are 10 students registered in Section BDS-1A. He wants an another array of same size where marks for failed students within range [0-5] are stored. Write a program for the given scenario. You program should exit if user enters -1 and will display the marks entered along with average of each array.
```c
#include <stdio.h>
int main() {
    
    int marks[10];
    int pass[10];
    int fail[10];
    int i, p= 0, f= 0;
    float sumP= 0, sumF= 0;

    printf("Enter marks (0-10) (Enter -1 to stop) :\n ");
    for(i = 0; i < 10; i++) {
        scanf("%d", &marks[i]);

        if(marks[i] == -1)
            break;

        if(marks[i] >= 5 && marks[i] <= 10) {
            pass[p] = marks[i];
            sumP += marks[i];
            p++;
        }
        else if(marks[i] >= 0 && marks[i] < 5) {
            fail[f] = marks[i];
            sumF += marks[i];
            f++;
        }
    }
    printf("\nPass Marks: ");
    for(i = 0; i < p; i++)
        printf("%d ", pass[i]);

    if(p > 0)
        printf("\nAverage Pass = %.2f\n", sumP / p);
    printf("\nFail Marks: ");
    
    for(i = 0; i < f; i++)
        printf("%d ", fail[i]);
    if(f > 0)
        printf("\nAverage Fail = %.2f\n", sumF / f);

    return 0;
}
```
### 4) Your class teacher asks you to develop a program that can help in converting mixed-case messages entered by users. The program should read a sentence using scanf(&quot;%[^\n]&quot;, str); and then convert all lowercase letters to uppercase and all uppercase letters to lowercase, without using any string library functions. Finally, display the converted message back to the user.
```c
#include <stdio.h>
int main() {
    
    char str[100];
    int i;
    printf("Enter sentence: ");
    scanf("%[^\n]", str);

    for(i = 0; str[i] != '\0'; i++) {
        if(str[i] >= 'A' && str[i] <= 'Z')
            str[i] = str[i] + 32;
        else if(str[i] >= 'a' && str[i] <= 'z')
            str[i] = str[i] - 32;
    }
    printf("Output: %s", str);

    return 0;
}
```
### 5) Write a program that reads 10 integers into an array. Finds and prints the difference (max - min) between the largest and smallest elements.
```c
#include <stdio.h>
int main() {
    int arr[10];
    int i, max, min, diff;

    printf("Enter 10 integers:\n");
    for(i = 0; i < 10; i++) {
        scanf("%d", &arr[i]);
    }
    max = min = arr[0];

    for(i = 1; i < 10; i++) {
        if(arr[i] > max)
            max = arr[i];
        if(arr[i] < min)
            min = arr[i];
    }
    diff = max - min;
    printf("Difference (max - min) = %d", diff);

    return 0;
}
```
### 6) You are assisting your English language teacher who wants to analyze how many vowels and consonants appear in students’ submitted words. Write a program that reads a single word using scanf(&quot;%s&quot;, str); and counts the number of vowels and consonants in it without using any string library functions like strlen(). The program should then display both counts on the screen.
```c
#include <stdio.h>
int main() {
    
    char str[50];
    int i = 0;
    int vowels = 0;
    int consonants = 0;

    printf("Enter a word: ");
    scanf("%s", str);

    while(str[i] != '\0') {
        if(str[i]=='a'||str[i]=='e'||str[i]=='i'||str[i]=='o'||str[i]=='u'||
          str[i]=='A'||str[i]=='E'||str[i]=='I'||str[i]=='O'||str[i]=='U')
            vowels++;
        else
            consonants++;
        i++;
    }
    printf("Vowels = %d\n", vowels);
    printf("Consonants = %d\n", consonants);

    return 0;
}
```
### 7) You are working in a data management department where you are asked to remove duplicate entries from a list of recorded IDs. Write a program that takes 10 integers from the user and stores them in an array. The program should replace every duplicate element (after its first occurrence) with -1 to mark it as a duplicate and then display the final updated array on the screen.
```c
#include <stdio.h>
int main() {
    int arr[10];
    int i, j;

    printf("Enter 10 integers: ");
    for(i = 0; i < 10; i++) {
        scanf("%d", &arr[i]);
    }
    for(i = 0; i < 10; i++) {
        for(j = i + 1; j < 10; j++) {
            if(arr[i] == arr[j]) {
                arr[j] = -1;  
    }
        }
    }
    printf("Output: ");
    for(i = 0; i < 10; i++) {
        printf("%d ", arr[i]);
    }

    return 0;
}
```
### 8) Write a program that reads a string using scanf(&quot;%[^A-Za-z]&quot;, str); so that it accepts and stores all characters except alphabets. The program should then display the entered non-alphabetic characters on the screen.
```c
#include <stdio.h>
int main() 
{
    char str[100], output[100];
    int i = 0, j = 0;

    printf("Enter a string: ");
    scanf("%[^\n]", str); 

    while(str[i] != '\0') {
        if(!((str[i] >= 'a' && str[i] <= 'z') || (str[i] >= 'A' && str[i] <= 'Z'))) {
            output[j] = str[i]; 
            j++;
        }
        i++;
    }
    output[j] = '\0'; 
    printf("Output: %s\n", output);

    return 0;
}
```
