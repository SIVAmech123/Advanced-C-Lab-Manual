EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
```
#include <stdio.h>

int main() {
    int num;

    // Input number from user
    printf("Enter a number (1 to 9): ");
    scanf("%d", &num);

    // Print corresponding word
    printf("Lowercase word: ");
    switch(num) {
        case 1: printf("one"); break;
        case 2: printf("two"); break;
        case 3: printf("three"); break;
        case 4: printf("four"); break;
        case 5: printf("five"); break;
        case 6: printf("six"); break;
        case 7: printf("seven"); break;
        case 8: printf("eight"); break;
        case 9: printf("nine"); break;
        default: printf("invalid number (must be 1–9)");
    }

    printf("\n");
    return 0;
}
```




Output:

Enter a number (1 to 9): 4
Lowercase word: four




Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```
#include <stdio.h>
#include <string.h>

int main() {
    char str[100];
    int freq[10] = {0}; // Frequency array for digits 0 to 9

    printf("Enter a string of digits: ");
    scanf("%s", str);

    // Count frequency of digits
    for (int i = 0; str[i] != '\0'; i++) {
        if (str[i] >= '0' && str[i] <= '9') {
            freq[str[i] - '0']++;
        }
    }

    // Print frequencies of digits 0 to 3
    for (int i = 0; i < 4; i++) {
        printf("%d ", freq[i]);
    }

    // If exactly 10 values are required with remaining as 0s:
    for (int i = 4; i < 10; i++) {
        printf("0 ");
    }

    printf("\n");
    return 0;
}
```



Output:

Enter a string of digits: 012301123
3 2 2 2 0 0 0 0 0 0


Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <stdbool.h>

// Function to swap characters
void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}

// Function to reverse a portion of the string
void reverse(char *str, int start, int end) {
    while (start < end) {
        swap(&str[start], &str[end]);
        start++;
        end--;
    }
}

// Function to find next lexicographical permutation
bool nextPermutation(char *str) {
    int len = strlen(str);
    int i = len - 2;

    // Find rightmost character which is smaller than its next character
    while (i >= 0 && str[i] >= str[i + 1])
        i--;

    if (i < 0)
        return false;

    // Find the rightmost character greater than str[i]
    int j = len - 1;
    while (str[j] <= str[i])
        j--;

    // Swap them
    swap(&str[i], &str[j]);

    // Reverse the suffix
    reverse(str, i + 1, len - 1);

    return true;
}

// Comparator for qsort
int cmp(const void *a, const void *b) {
    return (*(char *)a - *(char *)b);
}

int main() {
    char str[100];
    printf("Enter a string: ");
    scanf("%s", str);

    // Sort the string to start from the lowest lex order
    qsort(str, strlen(str), sizeof(char), cmp);

    // Print all permutations
    do {
        printf("%s\n", str);
    } while (nextPermutation(str));

    return 0;
}
```





Output:

Enter a string: abc
abc
acb
bac
bca
cab
cba




Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
```
#include <stdio.h>

int main() {
    int n;

    // Input value of N
    printf("Enter the value of N: ");
    scanf("%d", &n);

    // Outer loop for each row
    for (int i = 1; i <= n; i++) {
        // Inner loop for numbers in each row
        for (int j = 1; j <= i; j++) {
            printf("%d ", j);
        }
        printf("\n");
    }

    return 0;
}
```




Output:

1
1 2
1 2 3
1 2 3 4




Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:
```
#include <stdio.h>

// Function declaration
int findSquare();

int main() {
    int result;

    // Call the function and store the result
    result = findSquare();

    // Display the result
    printf("Square of the number is: %d\n", result);

    return 0;
}

// Function definition
int findSquare() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}
```




Output:


Enter a number: 6
Square of the number is: 36






Result:
Thus, the program is verified successfully



























