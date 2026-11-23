#include <stdio.h>

struct Student
{
    int rollno;
    char name[50];
    float marks;
    char grade;
};

int main()
{
    struct Student s[100];
    int n, i;

    printf("Enter number of students: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++)
    {
        printf("\nEnter details of student %d:\n", i + 1);

        printf("Enter Roll Number: ");
        scanf("%d", &s[i].rollno);

        printf("Enter Name: ");
        scanf(" %[^\n]", s[i].name);

        printf("Enter Marks: ");
        scanf("%f", &s[i].marks);

        if(s[i].marks >= 90)
            s[i].grade = 'A';
        else if(s[i].marks >= 75)
            s[i].grade = 'B';
        else if(s[i].marks >= 60)
            s[i].grade = 'C';
        else if(s[i].marks >= 40)
            s[i].grade = 'D';
        else
            s[i].grade = 'F';
    }

    printf("\n------ STUDENT RESULTS ------\n");

    printf("\n%-10s %-25s %-10s %-8s\n",
        "Roll No.", "Name", "Marks", "Grade");

    printf("-------------------------------------------------------\n");

    for(i = 0; i < n; i++)
    {
        printf("%-10d %-25.25s %-10.2f %-8c\n",
               s[i].rollno,
               s[i].name,
               s[i].marks,
               s[i].grade);
    }

    return 0;
}
