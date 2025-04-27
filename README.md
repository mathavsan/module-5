# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    float length, breadth, area;
    float *ptr_length, *ptr_breadth;

    printf("Enter the length and breadth of the rectangle: ");
    scanf("%f %f", &length, &breadth);

    ptr_length = &length;
    ptr_breadth = &breadth;

    area = (*ptr_length) * (*ptr_breadth);
    printf("Area of the rectangle: %.2f\n", area);

    return 0;
}
```

## OUTPUT
```
Enter the length and breadth of the rectangle: 5 3
Area of the rectangle: 15.00
```		       	


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    char *str;

    str = (char *)malloc(8 * sizeof(char));  // Allocating memory
    if (str == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }

    // Copy "WELCOME" into the allocated memory
    str = "WELCOME";
    printf("%s\n", str);

    // Free allocated memory
    free(str);

    return 0;
}
```
## OUTPUT
```
WELCOME
```



## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct student {
    char name[50];
    int roll_no;
    float marks;
};

int main() {
    struct student s;

    printf("Enter student name: ");
    scanf("%s", s.name);
    printf("Enter roll number: ");
    scanf("%d", &s.roll_no);
    printf("Enter marks: ");
    scanf("%f", &s.marks);

    printf("\nStudent Information:\n");
    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.roll_no);
    printf("Marks: %.2f\n", s.marks);

    return 0;
}
```

## OUTPUT
```
Enter student name: John
Enter roll number: 123
Enter marks: 85.5

Student Information:
Name: John
Roll Number: 123
Marks: 85.50
```
## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct employee {
    char name[50];
    int id;
    float basic_salary, hra, da, gross_salary;
};

int main() {
    struct employee e[3];
    for (int i = 0; i < 3; i++) {
        printf("\nEnter details for Employee %d:\n", i + 1);
        printf("Enter name: ");
        scanf("%s", e[i].name);
        printf("Enter ID: ");
        scanf("%d", &e[i].id);
        printf("Enter Basic Salary: ");
        scanf("%f", &e[i].basic_salary);

        e[i].hra = 0.2 * e[i].basic_salary;
        e[i].da = 0.1 * e[i].basic_salary;
        e[i].gross_salary = e[i].basic_salary + e[i].hra + e[i].da;

        printf("\nEmployee %d Details:\n", i + 1);
        printf("Name: %s\n", e[i].name);
        printf("ID: %d\n", e[i].id);
        printf("Gross Salary: %.2f\n", e[i].gross_salary);
    }

    return 0;
}
```

 ## OUTPUT
```
Enter details for Employee 1:
Enter name: John
Enter ID: 101
Enter Basic Salary: 50000

Employee 1 Details:
Name: John
ID: 101
Gross Salary: 60000.00

Enter details for Employee 2:
Enter name: Alice
Enter ID: 102
Enter Basic Salary: 45000

Employee 2 Details:
Name: Alice
ID: 102
Gross Salary: 54000.00

Enter details for Employee 3:
Enter name: Bob
Enter ID: 103
Enter Basic Salary: 60000

Employee 3 Details:
Name: Bob
ID: 103
Gross Salary: 72000.00
```
 

## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>

struct student {
    char name[10];
    int rollno;
    int subject[5];
    int total;
    float average;
};

int main() {
    struct student s[2];
    int i, j;

    for (i = 0; i < 2; i++) {
        printf("Enter details for Student %d\n", i + 1);
        printf("Enter name: ");
        scanf("%s", s[i].name);
        printf("Enter roll number: ");
        scanf("%d", &s[i].rollno);

        s[i].total = 0;
        for (j = 0; j < 5; j++) {
            printf("Enter marks for subject %d: ", j + 1);
            scanf("%d", &s[i].subject[j]);
            s[i].total += s[i].subject[j];
        }

        s[i].average = s[i].total / 5.0;
        printf("Total Marks for %s: %d\n", s[i].name, s[i].total);
        printf("Average Marks for %s: %.2f\n", s[i].name, s[i].average);
    }

    return 0;
}
```

## OUTPUT
```
Enter details for Student 1
Enter name: John
Enter roll number: 1
Enter marks for subject 1: 85
Enter marks for subject 2: 90
Enter marks for subject 3: 78
Enter marks for subject 4: 88
Enter marks for subject 5: 92
Total Marks for John: 433
Average Marks for John: 86.60

Enter details for Student 2
Enter name: Alice
Enter roll number: 2
Enter marks for subject 1: 80
Enter marks for subject 2: 85
Enter marks for subject 3: 75
Enter marks for subject 4: 95
Enter marks for subject 5: 90
Total Marks for Alice: 425
Average Marks for Alice: 85.00
```
 

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


