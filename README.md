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
~~~c
#include <stdio.h>
int main() {
    float length, width, area;
    float *ptr_length, *ptr_width, *ptr_area;
    ptr_length = &length;
    ptr_width = &width;
    ptr_area = &area;
    printf("Enter the length of the rectangle: ");
    scanf("%f", ptr_length);
    printf("Enter the width of the rectangle: ");
    scanf("%f", ptr_width);
    *ptr_area = (*ptr_length) * (*ptr_width);
    printf("Area of the rectangle: %.2f\n", *ptr_area);
    return 0;
}
~~~

## OUTPUT
		       	
![Screenshot 2025-04-27 135909](https://github.com/user-attachments/assets/b8503851-dffe-4a61-8944-3866b9cfdf2f)


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
~~~c
#include <stdio.h>
#include <stdlib.h>
int main() {
    char *str = (char *)malloc(8 * sizeof(char)); 
    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }
    str = "WELCOME";
    printf("%s\n", str);
    return 0;
}
~~~

## OUTPUT

![Screenshot 2025-04-27 140228](https://github.com/user-attachments/assets/85f14507-e3d1-4e93-920d-b00b8990295b)


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
~~~c
#include <stdio.h>
struct Student {
    char name[50];
    int roll_number;
    float marks;
};
int main() {
    struct Student student1; 
    printf("Enter student name: ");
    fgets(student1.name, sizeof(student1.name), stdin);  
    printf("Enter roll number: ");
    scanf("%d", &student1.roll_number);
    printf("Enter marks: ");
    scanf("%f", &student1.marks);
    printf("\nStudent Information:\n");
    printf("Name: %s", student1.name);
    printf("Roll Number: %d\n", student1.roll_number);
    printf("Marks: %.2f\n", student1.marks);
    return 0;
}
~~~


## OUTPUT

![Screenshot 2025-04-27 140423](https://github.com/user-attachments/assets/b0569ecf-20db-4a0b-b0cf-d1d35a887120)


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
~~~c
#include <stdio.h>
struct Employee {
    char name[50];
    float basicPay;
    float hra;    // House Rent Allowance
    float da;     // Dearness Allowance
    float grossSalary;
};
void calculateGrossSalary(struct Employee* emp) {
    // Gross Salary = Basic Pay + HRA + DA
    emp->grossSalary = emp->basicPay + emp->hra + emp->da;
}

int main() {
    struct Employee employees[3]; 
    for (int i = 0; i < 3; i++) {
        printf("Enter information for Employee %d\n", i + 1);
        printf("Enter name: ");
        fgets(employees[i].name, sizeof(employees[i].name), stdin);  // Input name
        printf("Enter basic pay: ");
        scanf("%f", &employees[i].basicPay);
        printf("Enter HRA (House Rent Allowance): ");
        scanf("%f", &employees[i].hra);
        printf("Enter DA (Dearness Allowance): ");
        scanf("%f", &employees[i].da);
        getchar();
        calculateGrossSalary(&employees[i]);
        printf("\n");
    }
    printf("\nEmployee Information and Gross Salary:\n");
    for (int i = 0; i < 3; i++) {
        printf("Employee %d: \n", i + 1);
        printf("Name: %s", employees[i].name);
        printf("Basic Pay: %.2f\n", employees[i].basicPay);
        printf("HRA: %.2f\n", employees[i].hra);
        printf("DA: %.2f\n", employees[i].da);
        printf("Gross Salary: %.2f\n", employees[i].grossSalary);
        printf("\n");
    }
    return 0;
}
~~~


 ## OUTPUT

 ![Screenshot 2025-04-27 141028](https://github.com/user-attachments/assets/a71d2a08-6c24-4a9a-be0c-7288d2507eb8)


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
~~~c
#include <stdio.h>
struct Student {
    char name[50];
    int marks[5];
    int total;
    float average;
};
void calculateTotalAndAverage(struct Student* student) {
    student->total = 0;
    for (int i = 0; i < 5; i++) {
        student->total += student->marks[i];
    }
    student->average = student->total / 5.0;
}

int main() {
    struct Student student1; 
    printf("Enter student name: ");
    fgets(student1.name, sizeof(student1.name), stdin);  // Read name (including spaces)
    printf("Enter marks for 5 subjects:\n");
    for (int i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%d", &student1.marks[i]);
    }
    calculateTotalAndAverage(&student1);
    printf("\nStudent Information:\n");
    printf("Name: %s", student1.name);
    printf("Total Marks: %d\n", student1.total);
    printf("Average Marks: %.2f\n", student1.average);
    return 0;
}
~~~


## OUTPUT

![Screenshot 2025-04-27 141401](https://github.com/user-attachments/assets/7d224153-3a0e-4040-9aa3-9e2bc21b7882)

 

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


