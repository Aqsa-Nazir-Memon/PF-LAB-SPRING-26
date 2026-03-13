## Question 1: Classroom Marks System
```c
#include <stdio.h>
int main() {
    int marks[4][3] = {
        {80, 75, 90},
        {60, 70, 85},
        {88, 92, 79},
        {55, 65, 70}
    };
    int i, j;
    int total;
    float average;
    printf("Total Marks of Each Student:\n");

    for(i = 0; i < 4; i++) {
        total = 0;

        for(j = 0; j < 3; j++) {
            total = total + marks[i][j];
        }

        printf("Student %d Total = %d\n", i + 1, total);
    }
    printf("\nAverage Marks of Each Subject:\n");
    
    for(j = 0; j < 3; j++) {
        total = 0;

        for(i = 0; i < 4; i++) {
            total = total + marks[i][j];
        }
        average = total / 4.0;

        printf("Subject %d Average: %.2f\n", j + 1, average);
    }
    return 0;
}
```
## Question 2: Cinema Seat Booking
```c
#include <stdio.h>
int main() {
    int seats[5][6] = {
        {1,0,1,0,0,1},
        {1,1,0,0,1,0},
        {0,0,0,1,0,0},
        {1,1,1,0,1,0},
        {0,0,1,0,0,0}
    };
    int i, j;
    int avail= 0;
    int booked;
    int max= 0;
    int row= 0;
    for(i = 0; i < 5; i++) {
        for(j = 0; j < 6; j++) {
            if(seats[i][j] == 0) {
                avail++;
            }
        }
    }
    printf("Total Available Seats: %d\n", avail);
    for(i = 0; i < 5; i++) {
        booked = 0;
        for(j = 0; j < 6; j++) {
            if(seats[i][j] == 1) {
                booked++;
            }
        }
        if(booked > max) {
            max= booked;
            row= i + 1;
        }
    }
    printf("Row with Maximum Booked Seats is Row %d\n", row);

    return 0;
}
```
## Question 3: Temperature Monitoring System
```c
#include <stdio.h>

int main() {
    int temp[7][3] = {
        {30,35,28},
        {31,36,29},
        {29,34,27},
        {32,37,30},
        {33,38,31},
        {30,36,29},
        {31,35,28}
    };

    int i,j;
    int high = temp[0][0];
    int sum;
    float avg;
    for(i=0;i<7;i++)
    {
        for(j=0;j<3;j++)
        {
            if(temp[i][j] > high)
            {
                high = temp[i][j];
            }
        }
    }
    printf("Highest Temperature: %d\n", high);
    printf("\nAverage Temperature of Each Day:\n");

    for(i=0;i<7;i++)
    {
        sum = 0;
        for(j=0;j<3;j++)
        {
            sum = sum + temp[i][j];
        }
        avg = sum / 3.0;
        printf("Day %d Average: %.2f\n", i+1, avg);
    }

    return 0;
}
```
## Question 4:
```c
#include <stdio.h>

int main()
{
    int A[3][3] = {
        {1,2,3},
        {0,4,5},
        {1,0,6}
    };
    int T[3][3], C[3][3], Adj[3][3];
    float Inv[3][3];
    int i,j;
    int det;
    printf("Original Matrix:\n");
    for(i=0;i<3;i++)
    {
        for(j=0;j<3;j++)
        {
            printf("%d ",A[i][j]);
        }
        printf("\n");
    }
    printf("\nTranspose Matrix:\n");
    for(i=0;i<3;i++)
    {
        for(j=0;j<3;j++)
        {
            T[i][j] = A[j][i];
            printf("%d ",T[i][j]);
        }
        printf("\n");
    }
    det = A[0][0]*(A[1][1]*A[2][2] - A[1][2]*A[2][1]) 
           - A[0][1]*(A[1][0]*A[2][2] - A[1][2]*A[2][0])
               + A[0][2]*(A[1][0]*A[2][1] - A[1][1]*A[2][0]);

    printf("\nDeterminant: %d\n",det);

    C[0][0] =  (A[1][1]*A[2][2] - A[1][2]*A[2][1]);
    C[0][1] = -(A[1][0]*A[2][2] - A[1][2]*A[2][0]);
    C[0][2] =  (A[1][0]*A[2][1] - A[1][1]*A[2][0]);

    C[1][0] = -(A[0][1]*A[2][2] - A[0][2]*A[2][1]);
    C[1][1] =  (A[0][0]*A[2][2] - A[0][2]*A[2][0]);
    C[1][2] = -(A[0][0]*A[2][1] - A[0][1]*A[2][0]);

    C[2][0] =  (A[0][1]*A[1][2] - A[0][2]*A[1][1]);
    C[2][1] = -(A[0][0]*A[1][2] - A[0][2]*A[1][0]);
    C[2][2] =  (A[0][0]*A[1][1] - A[0][1]*A[1][0]);

    printf("\nCofactor Matrix:\n");
    for(i=0;i<3;i++)
    {
        for(j=0;j<3;j++)
        {
            printf("%d ",C[i][j]);
        }
        printf("\n");
    }
    printf("\nAdjoint Matrix:\n");
    for(i=0;i<3;i++)
    {
        for(j=0;j<3;j++)
        {
            Adj[i][j] = C[j][i];
            printf("%d ",Adj[i][j]);
        }
        printf("\n");
    }
    printf("\nInverse Matrix:\n");
    for(i=0;i<3;i++)
    {
        for(j=0;j<3;j++)
        {
            Inv[i][j] = Adj[i][j] / (float)det;
            printf("%.2f ",Inv[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```
## Question 5:
```c
#include <stdio.h>

int main() {
    int a[5][5];
    int r, c, i, j;

    int zero=1, identity=1, diag=1, scalar=1;
    int upper=1, lower=1, sym=1, skew=1;

    printf("Enter rows and columns: ");
    scanf("%d %d", &r, &c);

    printf("Enter matrix elements:\n");
    for(i=0;i<r;i++)
        for(j=0;j<c;j++)
            scanf("%d",&a[i][j]);

    if(r==c)
        printf("Square Matrix\n");
    else
        printf("Rectangular Matrix\n");

    if(r==1) printf("Row Matrix\n");
    if(c==1) printf("Column Matrix\n");

    int d = (r>0 && c>0) ? a[0][0] : 0;

    for(i=0;i<r;i++) {
        for(j=0;j<c;j++) {
            if(a[i][j] != 0) zero=0;

            if(i != j && a[i][j] != 0) {
                diag=0;
                identity=0;
            }

            if(i != j) scalar=0;

            if(i>j && a[i][j] != 0) upper=0;
            if(i<j && a[i][j] != 0) lower=0;

            if(r==c && a[i][j] != a[j][i]) sym=0;
            if(r==c && a[i][j] != -a[j][i]) skew=0;
        }
        if(a[i][i] != d) scalar=0;
    }

    if(zero) printf("Zero / Null Matrix\n");
    if(identity) printf("Identity Matrix\n");
    if(diag) printf("Diagonal Matrix\n");
    if(scalar) printf("Scalar Matrix\n");
    if(upper) printf("Upper Triangular Matrix\n");
    if(lower) printf("Lower Triangular Matrix\n");
    if(sym && r==c) printf("Symmetric Matrix\n");
    if(skew && r==c) printf("Skew-Symmetric Matrix\n");

    if(r==2 && c==2) {
        int det = a[0][0]*a[1][1] - a[0][1]*a[1][0];
        if(det==0) printf("Singular Matrix\n");
        else printf("Non-Singular Matrix\n");
    }

    return 0;
}
```
## Question 6: 
```c
#include <stdio.h>
int main() {
    int A[3][3], B[3][3], C[3][3];
    int r1, c1, r2, c2;
    int i, j, k;
    
    printf("Enter rows and columns for first matrix: ");
    scanf("%d %d", &r1, &c1);
    printf("Enter rows and columns for second matrix: ");
    scanf("%d %d", &r2, &c2);

    if(c1 != r2) {
        printf("Matrix multiplication not possible! \n");
        return 0;
    }
    printf("Enter elements of first matrix:\n");
    for(i=0;i<r1;i++)
        for(j=0;j<c1;j++)
            scanf("%d", &A[i][j]);
    printf("Enter elements of second matrix:\n");
    for(i=0;i<r2;i++)
        for(j=0;j<c2;j++)
            scanf("%d", &B[i][j]);
            
    for(i=0;i<r1;i++)
        for(j=0;j<c2;j++)
            C[i][j] = 0;

    for(i=0;i<r1;i++) {
        for(j=0;j<c2;j++) {
            for(k=0;k<c1;k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
        }
    }
    printf("\nResult Matrix C (A x B):\n");
    for(i=0;i<r1;i++) {
        for(j=0;j<c2;j++)
            printf("%d ", C[i][j]);
        printf("\n");
    }

    return 0;
}
```
