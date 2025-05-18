# EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
## Aim:
To write a C program print the lowercase English word corresponding to the number
## Algorithm:
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
 
## Program:
```
#include<stdio.h>
int main()
{
    int n;
    scanf("%d",&n);
    switch(n)
    {
        case 71:
        printf("seventy one\n");
        break;
        case 72:
        printf("seventy two\n");
        break;
        case 73:
        printf("seventy three");
        break;
        case 74:
        printf("seventy four");
        break;
        case 75:
        printf("seventy five");
        break;
        case 76:
        printf("seventy six");
        break;
        case 77:
        printf("seventy seven");
        break;
        case 78:
        printf("seventy eight");
        break;
        case 79:
        printf("seventy nine");
        break;
        default:
        printf("Greater than 79");
        break;
    }
    return 0;
}
```
## Output:

![image](https://github.com/user-attachments/assets/ad76db39-2383-49b7-8d9a-4c58227ac15c)

## Result:
Thus, the program is verified successfully
 
# EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
## Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
## Program:
```
#include <stdio.h>
#include <string.h>
int main() 
{
    char s[50];  
    int count[3] = {0}; 
    scanf("%s", s);
    for (int i = 0; i < strlen(s); i++) 
    {
        if (s[i] >= '0' && s[i] <= '3')
        {  
            count[s[i] - '0']++;  
        }
    }
    for (int i = 0; i < 3; i++) 
    {
        printf("%d ", count[i]);
    }
    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/45fcf46d-7e53-4864-85d0-dedc3862d84f)

## Result:
Thus, the program is verified successfully

# EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
## Aim:
To write a C program to print all of its permutations in strict lexicographical order.

## Algorithm:
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
 
## Program:
```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
void swap(char **a, char **b) 
{
    char *temp = *a;
    *a = *b;
    *b = temp;
}
int next_permutation(char *arr[], int n)
{
    int i = n - 2;
    while (i >= 0 && strcmp(arr[i], arr[i + 1]) >= 0) 
    {
        i--;
    }
    if (i < 0) 
    {
        return 0; 
    }
    int j = n - 1;
    while (strcmp(arr[i], arr[j]) >= 0) 
    {
        j--;
    }
    swap(&arr[i], &arr[j]);
    int left = i + 1, right = n - 1;
    while (left < right) {
        swap(&arr[left], &arr[right]);
        left++;
        right--;
    }
    return 1;
}
int main()
{
    int n;
    scanf("%d", &n);
    char *s[n];  
    for (int i = 0; i < n; i++) 
    {
        s[i] = (char *)malloc(11 * sizeof(char));  
        scanf("%s", s[i]);
    }
    qsort(s, n, sizeof(char *), (int (*)(const void *, const void *)) strcmp);
    do 
    {
        for (int i = 0; i < n; i++) 
        {
            printf("%s ", s[i]);
        }
        printf("\n");
    } while (next_permutation(s, n));
    for (int i = 0; i < n; i++) 
    {
        free(s[i]);
    }
    return 0;
}
```

## Output:


![image](https://github.com/user-attachments/assets/1685a2dd-9a05-4b9b-88b8-8171a1d096a2)

## Result:
Thus, the program is verified successfully
 
# EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW.
## Aim:
 To write a C program to print a pattern of numbers from 1 to n as shown below.
## Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
## Program:
```
#include<stdio.h>
int main()
{
    int n,i,j;
    scanf("%d",&n);
    int len=2*n-1;
    for(i=0;i<len;i++)
    {
        for(j=0;j<len;j++)
        {
            int min=i<j?i:j;
            min=min<len-i-1?min:len-i-1;
            min=min<len-j-1?min:len-j-1;
            printf("%d ",n-min);
        }
        printf("\n");
    }
    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/dee39f86-f283-4d6a-810f-1d5f6652cb55)

## Result:
Thus, the program is verified successfully

# EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

## Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

## Algorithm:

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

## Program:
```
#include <stdio.h>
int square() {
    int num, sqr;
    printf("Enter a number: ");
    scanf("%d", &num);
    sqr = num * num;
    return sqr;
}

int main() {
    int result;
    result = square();
    printf("Square of the number is: %d\n", result);
    return 0;
}
```

## Output:
![image](https://github.com/user-attachments/assets/3f28fa67-a4db-4334-9141-e3c1e410309b)

## Result:
Thus, the program is verified successfully
