# EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
## Aim:
To write a C program to create a function to find the greatest number

## Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:
```
#include <stdio.h>

int max_of_four(int a, int b, int c, int d) {
    int max = a;
    if(b > max) max = b;
    if(c > max) max = c;
    if(d > max) max = d;
    return max;
}

int main() {
    int n1, n2, n3, n4, greater;
    printf("Enter four numbers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    greater = max_of_four(n1, n2, n3, n4);
    printf("The greatest number is: %d\n", greater);
    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/b54bd6a8-0f2a-433b-ae54-f0ed6e84cfe5)



## Result:
Thus, the program  that create a function to find the greatest number is verified successfully.

# EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
## Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

## Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
## Program:
```
#include <stdio.h>

void calculate_the_maximum(int n, int k) {
    int max_and = 0, max_or = 0, max_xor = 0;
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int bitwise_and = i & j;
            int bitwise_or = i | j;
            int bitwise_xor = i ^ j;
            if (bitwise_and < k && bitwise_and > max_and) {
                max_and = bitwise_and;
            }
            if (bitwise_or < k && bitwise_or > max_or) {
                max_or = bitwise_or;
            }
            if (bitwise_xor < k && bitwise_xor > max_xor) {
                max_xor = bitwise_xor;
            }
        }
    }
    printf("%d\n%d\n%d\n", max_and, max_or, max_xor);
}

int main() {
    int n, k;
    scanf("%d %d", &n, &k);
    calculate_the_maximum(n, k);
    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/8853e045-1a40-44ca-a1d8-727574c5ff7b)


## Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
# EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
## Aim:
To write a C program to write the logic for the requests

## Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

int** shelves;
int* books_per_shelf;

void add_book(int x, int pages) {
    int count = books_per_shelf[x];
    shelves[x] = (int*)realloc(shelves[x], (count + 1) * sizeof(int));
    shelves[x][count] = pages;
    books_per_shelf[x]++;
}

void print_book_pages(int x, int y) {
    printf("%d\n", shelves[x][y]);
}

void print_book_count(int x) {
    printf("%d\n", books_per_shelf[x]);
}

int main() {
    int n, q;
    scanf("%d", &n);
    scanf("%d", &q);

    shelves = (int**)malloc(n * sizeof(int*));
    books_per_shelf = (int*)calloc(n, sizeof(int));

    for (int i = 0; i < n; i++) {
        shelves[i] = NULL;
    }

    for (int i = 0; i < q; i++) {
        int type;
        scanf("%d", &type);

        if (type == 1) {
            int x, y;
            scanf("%d %d", &x, &y);
            add_book(x, y);
        }
        else if (type == 2) {
            int x, y;
            scanf("%d %d", &x, &y);
            print_book_pages(x, y);
        }
        else if (type == 3) {
            int x;
            scanf("%d", &x);
            print_book_count(x);
        }
    }

    
    for (int i = 0; i < n; i++) {
        free(shelves[i]);
    }
    free(shelves);
    free(books_per_shelf);

    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/2fc4faa8-41d4-462f-8a64-bfd4d22376ec)

## Result:
Thus, the program to write the logic for the requests is verified successfully.

# EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
## Aim:
To write a C program print the sum of the integers in the array.

## Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.

## Program:
```
#include <stdio.h>

int main() {
    int n, sum = 0;
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    int a[n];
    printf("Enter the elements:\n");
    for(int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }
    printf("Sum of array elements: %d\n", sum);
    return 0;
}
```

## Output:
![image](https://github.com/user-attachments/assets/b50277df-984c-4d38-a3d3-1ed35fdf263e)

## Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


# EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE

## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



## Program:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char sentence[1000];
    int count = 0, inWord = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    for(int i = 0; sentence[i] != '\0'; i++) {
        if(!isspace(sentence[i]) && inWord == 0) {
            inWord = 1;
            count++;
        } else if(isspace(sentence[i])) {
            inWord = 0;
        }
    }

    printf("Number of words: %d\n", count);
    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/7604661c-088c-4542-b4d8-ed8fc2af2102)

## Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
