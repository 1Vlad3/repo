#include <stdlib.h>

#include <math.h>

#define n 5

void sort (int a[n][n]);

void calc (int a[n][n]);

main ()

{

int a[n][n];

int i,j;

for(i=0;i<n;i++)

{

for(j=0;j<n;j++)

{

printf ("Enter element [%d][%d] massiva: " ,i+1,j+1);

scanf ("%d", &a[i][j]);

}

}

for (i=0; i<n; i++)

{

for (j=0;j<n;j++)

{

printf ("%d\t", a[i][j]);

}

printf ("\n");

}

sort (a);

printf ("\n new matrix \n");

for (i=0;i<n;i++)

{

for (j=0;j<n;j++)

{

printf ("%d\t", a[i][j]);

}

printf ("\n");

}

calc (a);

}

void calc (int a [n][n])

{

int i,j;

double f,F;

F=0.0;

for (i=0;i<n;i++)

{

f=1.0;

for (j=0;j<n;j++)

{

if (j>i)

{

f*=(fabs(a[i][j]));

}

}

f=pow(f,1.0/(n-i));

F+=f;

printf ("Serednie geometrychne elementiv %d riadka=%lf\n", i+1,f);

}

printf ("Suma serednih geometrychnyh elementiv riadkiv=%lf\n",F);

}

void sort (int a[n][n])

{

int i,j,k,x;

for(j=0;j<n;j++)

{

for(i=1;i<n;i++)

{

x=a[i][j];

k=i-1;

while (a[k][j]>x&&k>=0)

{

a[k+1][j]=a[k][j];

k--;

}

a[k+1][j]=x;

}

}

}
