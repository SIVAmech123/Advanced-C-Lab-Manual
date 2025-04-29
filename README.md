EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include <stdio.h>
#include <string.h>

#define MAX 100

// Structure to hold person details
struct Person {
    char name[50];
    int age;
};

int main() {
    struct Person people[MAX];
    int n, i;

    printf("Enter the number of people: ");
    scanf("%d", &n);

    // Input data
    for(i = 0; i < n; i++) {
        printf("\nEnter details for person %d:\n", i+1);
        printf("Name: ");
        scanf(" %[^\n]s", people[i].name);
        printf("Age: ");
        scanf("%d", &people[i].age);
    }

    // Check eligibility
    printf("\nVaccine Eligibility Results:\n");
    for(i = 0; i < n; i++) {
        printf("%s (Age %d): ", people[i].name, people[i].age);
        if(people[i].age >= 18)
            printf("Eligible for vaccination\n");
        else
            printf("Not eligible for vaccination\n");
    }

    return 0;
}
```


Output:
Enter the number of people: 2

Enter details for person 1:
Name: Alice
Age: 22

Enter details for person 2:
Name: Bob
Age: 15

Vaccine Eligibility Results:
Alice (Age 22): Eligible for vaccination
Bob (Age 15): Not eligible for vaccination





Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
```
#include <stdio.h>

// Define a structure to hold student marks
struct Student {
    int roll_no;
    char name[50];
    float marks;
};

// Function to display student details (structure as argument)
void displayStudent(struct Student s) {
    printf("Roll No: %d\n", s.roll_no);
    printf("Name   : %s\n", s.name);
    printf("Marks  : %.2f\n", s.marks);
}

// Function to return student with higher marks (structure as return type)
struct Student getTopper(struct Student s1, struct Student s2) {
    if(s1.marks > s2.marks)
        return s1;
    else
        return s2;
}

int main() {
    struct Student student1, student2, topper;

    // Input student 1 details
    printf("Enter details for Student 1:\n");
    printf("Roll No: ");
    scanf("%d", &student1.roll_no);
    printf("Name: ");
    scanf(" %[^\n]", student1.name);
    printf("Marks: ");
    scanf("%f", &student1.marks);

    // Input student 2 details
    printf("\nEnter details for Student 2:\n");
    printf("Roll No: ");
    scanf("%d", &student2.roll_no);
    printf("Name: ");
    scanf(" %[^\n]", student2.name);
    printf("Marks: ");
    scanf("%f", &student2.marks);

    // Display students
    printf("\n--- Student Details ---\n");
    displayStudent(student1);
    displayStudent(student2);

    // Get and display topper
    topper = getTopper(student1, student2);
    printf("\n--- Topper ---\n");
    displayStudent(topper);

    return 0;
}
```



Output:


Enter details for Student 1:
Roll No: 101
Name: Alice
Marks: 88.5

Enter details for Student 2:
Roll No: 102
Name: Bob
Marks: 91.2

--- Student Details ---
Roll No: 101
Name   : Alice
Marks  : 88.50
Roll No: 102
Name   : Bob
Marks  : 91.20

--- Topper ---
Roll No: 102
Name   : Bob
Marks  : 91.20





Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>

int main() {
    char filename[100];
    FILE *fp;
    char content[500];

    // Get file name from user
    printf("Enter the file name to write to: ");
    scanf("%s", filename);

    // Open file in write mode
    fp = fopen(filename, "w");
    if (fp == NULL) {
        printf("Error opening file!\n");
        return 1;
    }

    // Get content to write to file
    printf("Enter content to write to the file:\n");
    getchar(); // To consume leftover newline from scanf
    fgets(content, sizeof(content), stdin);

    // Write content to file
    fputs(content, fp);

    // Close the file
    fclose(fp);

    printf("File '%s' written successfully.\n", filename);
    return 0;
}
```




Output:

Enter the file name to write to: myfile.txt
Enter content to write to the file:
This is a test file.

File 'myfile.txt' written successfully.


Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>

int main() {
    char filename[100];
    FILE *fp;
    char content[500];

    // Step 1: Get file name from user
    printf("Enter the file name: ");
    scanf("%s", filename);

    // Step 2: Open file in write mode to create or overwrite it
    fp = fopen(filename, "w");
    if (fp == NULL) {
        printf("Error creating file!\n");
        return 1;
    }

    // Step 3: Write initial content to the file
    printf("Enter content to write to the file:\n");
    getchar();  // Clear newline from buffer
    fgets(content, sizeof(content), stdin);
    fputs(content, fp);
    fclose(fp);

    // Step 4: Open file in append mode to insert more text
    fp = fopen(filename, "a");
    if (fp == NULL) {
        printf("Error opening file for appending!\n");
        return 1;
    }

    printf("\nEnter additional text to insert into the file:\n");
    fgets(content, sizeof(content), stdin);
    fputs(content, fp);
    fclose(fp);

    printf("\nText written and inserted into '%s' successfully.\n", filename);
    return 0;
}
```






Output:

Enter the file name: notes.txt
Enter content to write to the file:
This is the original content.

Enter additional text to insert into the file:
This is the inserted text.

Text written and inserted into 'notes.txt' successfully.







Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:
```
#include <stdio.h>

// Define structure for Student
struct Student {
    char name[50];
    int roll_no;
    float marks;
};

int main() {
    struct Student s;

    // Input student details
    printf("Enter student name: ");
    scanf(" %[^\n]s", s.name);
    printf("Enter roll number: ");
    scanf("%d", &s.roll_no);
    printf("Enter marks: ");
    scanf("%f", &s.marks);

    // Display student details
    printf("\n--- Student Details ---\n");
    printf("Name      : %s\n", s.name);
    printf("Roll No   : %d\n", s.roll_no);
    printf("Marks     : %.2f\n", s.marks);

    return 0;
}
```




Output:

Enter student name: John Smith
Enter roll number: 101
Enter marks: 88.5

--- Student Details ---
Name      : John Smith
Roll No   : 101
Marks     : 88.50







Result:
Thus, the program is verified successfully
