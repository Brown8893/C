# A. 請使用三種迴圈方式撰寫完成計算1+5+9+...+401等差級數的總和之程式設計
## A_for
```
#include <stdio.h>
#include <stdlib.h> 
main() 
{
    int i = 1;
    int total = 0;
    for ( i = 1; i <= 401; i+=4 )
    {  
       total += i;
    }
    printf("1+5+9+...+401 等差級數總和為%d\n", total);
    getchar();
}
```
## A_while
```
#include <stdio.h>
#include <stdlib.h>
int main(int x)
{
 int i=1,total=0;
	  while(i<=401)
	    {
		  total+=i;
		  i+=4; 
            }
 printf("1+5+9+...+401 等差級數的總和為%d\n",total);
 getchar();
}
```
## A_dowhile
```
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int n,i=1,sum=0;
   printf("請輸入n值 (n>0): ");
   scanf("%d",&n);	
   do
   {
      sum+=i;
      i+=4;
   }
   while (i<=n);
   
   printf("1+5+9+...+401 等差級數總和為%d\n",sum);
   getchar();
}
```
# B. 函數設計題:完成底下計算次方函數 power(x,n):x**n，請使用三種loop及Recursion技術設計次方函數power(x,n): [power(2,5)==2*2*2*2*2=2**5=32]
## B_power_for
```
#include <stdio.h>
#include <stdlib.h>
double power(double, int);	
int main(void)
{
   double x;		
   int n;		

   printf("請輸入底數與次方:");	
   scanf("%lf,%d",&x,&n); 	
   printf("%lf的%d次方=%lf\n",x,n,power(x,n)); 

   system("pause");
   return 0;
}

double power(double base, int n)   
{
   int i;
   double pow=1.0;
   for(i=1;i<=n;i++)		
      pow=pow*base;
   return pow;
}
```
# B_power_while
```
#include <stdio.h>
#include <stdlib.h>
double power(double, int);	
int main(void)
{
   double x;		
   int n;		

   printf("請輸入底數與次方:");	
   scanf("%lf,%d",&x,&n); 	
   printf("%lf的%d次方=%lf\n",x,n,power(x,n)); 

   system("pause");
   return 0;
}

double power(double base, int n)   
{
   int i=1;
   double pow=1.0;
   while(i<=n)
	{
	i++ ; 	
      pow=pow*base;
    }
   return pow;
}
```
```
#include <stdio.h>
#include <stdlib.h>
double power(double, int);	
int main(void)
{
   double x;		
   int n;		

   printf("請輸入底數與次方:");	
   scanf("%lf,%d",&x,&n); 	
   printf("%lf的%d次方=%lf\n",x,n,power(x,n)); 

   system("pause");
   return 0;
}

double power(double base, int n)   
{
   int i=1;
   double pow=1.0;
   while(i<=n)
	{
	i++ ; 	
      pow=pow*base;
    }
   return pow;
}
```
# B_power_dowhile
```
#include<stdio.h>
#include<conio.h>
int main(void)
{
    int base, exponent,power, i;
    power = 1;
    i = 1;
    while(i <= 5)
    do
    {
        power = power * 2;
        i++;
    }
	while(i<=base);
    
    printf("Power : %d", power);
    return 0;
    getch();
}
```
# B_power_r
```
#include <stdio.h>

int power(int n1, int n2);

int main()
{
    int base=2, powerRaised=5, result;

 
    result = power(base, powerRaised);

    printf("%d**%d = %d", base, powerRaised, result);
    return 0;
}

int power(int base, int powerRaised)
{
    if (powerRaised != 0)
        return (base*power(base, powerRaised-1));
    else
        return 1;
}
```
# C_fac_for
```
#include <stdio.h>
 
int main()
{
  int c, n=5, fact = 1;
  for (c = 1; c <= n; c++)
    fact = fact * c;
 
  printf("Factorial of %d = %d\n", n, fact);
 
  return 0;
}
```
# C_fac_while
```
#include<stdio.h>
#include<conio.h>
int main(void)
{
    int n=5,i,f;
    f=i=1;
    while(i<=n)
    {
        f*=i;
        i++;
    }
    printf("The Factorial of %d is : %d",n,f);
    getch();
}
```
# C_fac_dowhile
```
 #include<stdio.h>
 #include<conio.h>
 int main(void)
 {
    long int i,n=5,fact=1; /*variable declaration */

    /* do loop start */
    i=1;
    do
    {
       fact*=i;
       i++;
    }
    while(i<=n);
 
    printf("Factorial = %ld\n",fact);
    getch();
    }
```
# C_fac_r
```
#include <stdio.h>
long int multiplyNumbers(int n);

int main()
{
   int n=5;
 
   printf("Factorial of %d = %ld", n, multiplyNumbers(n));
   return 0;
}
long int multiplyNumbers(int n)
{
   if (n >= 1)
       return n*multiplyNumbers(n-1);
   else
       return 1;
}
```
# D_fib_for
```
#include <stdio.h>
int main()
{
    int i, n, t1 = 0, t2 = 1, nextTerm;

    printf("Enter the number of terms: ");
    scanf("%d", &n);

    printf("Fibonacci Series: ");

    for (i = 1; i <= n; ++i)
    {
        printf("%d, ", t1);
        nextTerm = t1 + t2;
        t1 = t2;
        t2 = nextTerm;
    }
    return 0;
}
```
# D_fib_while
```
#include<stdio.h>
#include<conio.h>
main()
{
    int f1=0,f2=1,f3,i=3,len;
    printf("enter length of the  fibonacci series:");
    scanf("%d",&len);
    printf("%d\t%d",f1,f2); // It prints the starting two values
    while(i<=len)           // checks the condition
    {
        f3=f1+f2;               // performs add operation on previous two  values
        printf("\t%d",f3);      // It prints from third value to given length
        f1=f2;
        f2=f3;
        i=i+1;                  // incrementing the i value by 1
    }
    getch();
}
```
# D_fib_dowhile
```
#include<stdio.h>
#include<conio.h>
 
int main(void)
{
    int n,f,f1=-1,f2=1;
 
    printf("  Enter The Number Of Terms:");
    scanf("%d",&n);
     
    printf("  The Fibonacci Series is:");
     
    do
    {
        f=f1+f2;
        f1=f2;
        f2=f;
        printf("  \n %d",f);
        n--;
    }while(n>0);
    getch();
}
```
# D_fib_r
```
#include<stdio.h>
 
int Fibonacci(int);
 
int main()
{
   int n, i = 0, c;
 
   scanf("%d",&n);
 
   printf("Fibonacci series\n");
 
   for ( c = 1 ; c <= n ; c++ )
   {
      printf("%d\n", Fibonacci(i));
      i++; 
   }
 
   return 0;
}
 
int Fibonacci(int n)
{
   if ( n == 0 )
      return 0;
   else if ( n == 1 )
      return 1;
   else
      return ( Fibonacci(n-1) + Fibonacci(n-2) );
} 
```
