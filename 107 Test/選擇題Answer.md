# 基本語法題
```
下列敘述何者正確?
A.C程式由主函數組成
B.C程式由函數組成
C.C程式由函數和過程組成
D.C程式中的註解行由/ *，由* /結束
```
```
B
```

```
以下符號中不能用作使用者識別字的符號是?
(A)_256  (B)void  (C)scanf  (D)Struct
```
```
A
```
```
若有定義：int a=2,b=3,c=4；則接著執行完語法：a*=16+(b++)-(++c)；後，a,b,c的值分別為?
(A)28  3  5  (B)28  4  5  (C)32  4  5  (D)32  4  4
```
```
B
```
```
設int a=12 ， 則執行完語法 a+=a-=a*a後，a的值是?
(A)552  (B)264  (C)144 (D)-264
```
```
D
```
```
執行下面的程式後，total的值是(A)45   (B)48  (C)50  (D)55

#include <stdio.h>
main() 
{
    int i = 1;
    int total = 0;
    do
    {
       if ( i >=10 ) break;
       printf("數字: %d\n", i);
       total += i;
       i++;
    } while(1);
    printf("總和: %d\n", total);
    getchar();
}
```
```
A
```
```
執行下面的程式後，total的值是 (A)45   (B)48  (C)50  (D)55

#include <stdio.h>
main() 
{
    int i = 1;
    int total = 0;
    do
    {
       printf("數字: %d\n", i);
       total += i;
       i++;
       if ( i >= 10 ) break;
    } while(1);
    printf("總和: %d\n", total);
    getchar();
}
```
```
A
```
```
有一Recursive的C語言程式如下，試間f(3)=?
(A) 10 (B) 12  (C) 14 (D) I6 (E) 30

int f(int x)
{
	if(x<=1)
		   return 1;
	else
		return (x**2+f(x-1));
}
```
```
C
```
```
設有一副程式定義如下  
Function f(x,y:integer):integer,
begin
if y=0 then f=1;
else f:=f(x,y-1)*x;
end; 

若a，b均為正整數，則呼叫f(a，b)時的結果為:(A)a*b (B)a+b (C)a**b(代表a的b乘方) (D)a/b
```
```
C
```
# 程式設計題

```
01.修正底下程式錯誤,完成程式計算3到37的偶數和

#include <stdio.h>
main() 
{
    int i = 1;
    int total = 3;
    for ( i = 1; i <= 33; i++ )
    {  
       if ( (i % 2) == 0 ) continue;
       total += i;
    }
    printf("總和為: %d\n", total);
    getchar();
}
```
```
01.答
#include <stdio.h>
main() 
{
    int i = 1;
    int total = 0;
    for ( i = 3; i <= 37; i++ )
    {  
       if ( (i % 2) != 0 ) continue;
       total += i;
    }
    printf("總和為%d\n", total);
    getchar();
}
```
```
02.1+3+…+99的總和程式設計技術
[1]用三種迴圈方式撰寫1+3+…+101的總和。
[2]用Recursion方式撰寫1+3+…+99的總和。
```
```
02[1].a_for
#include <stdio.h>

int main() 
{

    int total=0 , i ;
    for ( i = 1; i <= 101; i++ )
    {  
       if ( (i % 2) == 0 ) continue;
       total += i;
    }
    printf("總和為：%d\n", total);
    return 0 ;
}
```
```
02[1].b
#include <stdio.h>
#include <stdlib.h> 
int main() 
{

    int sum=0 , i=0 ;
    while (sum<=101)
    {  
       sum+=1 ;
       
       if ( (sum % 2) == 0 ) continue;
       i += sum;
    }
    printf("總和為：%d\n", i);
    return 0 ;
}
```
```
02[1].c
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int n,i=1,sum=1; /* 設定迴圈初值 */
   do
   {
      printf("請輸入n值 (n>0): ");
      scanf("%d",&n);
   }
   while (n<=0);  /* 當n<=0時重複輸入n的值 */

   do
      sum+=i+=2;  /* 計算sum=sum+i之後，i的值再加1 */
   while (i < n); /* 當i<=n時執行累加的動作 */
   printf("1+3+...+%d=%d\n",n,sum);
   printf("%d\n",i);
   system("pause");
   return 0;
}
```
```
04.函數設計題:完成底下計算次方函數power(x,n):x**n
power(2,5)==2*2*2*2*2=2**5=32
power(2.11,5)==2.11*2.11*2.11*2.11*2.11=2.11**5

請使用下列loop及Recursion技術設計次方函數power(x,n):
power_for:使用for loop開發的次方函數
power_while:使用while loop開發的次方函數
power_doWhile:使用do While loop開發的次方函數
power_r:使用Recursion方式開發的次方函數
```
```
04_for
#include <stdio.h>
#include <stdlib.h>

double power_for(double, int);	
double power_while(double, int);
double power_doWhile(double, int);
double power_r(double, int);

int main(void)
{
   double x=2;		
   int n=5;		
   printf("%lf的%d次方是%lf\n",x,n,power_for(x,n)); 
   system("pause");
   return 0;
}

double power_for(double base, int n) 
{
   int i;
   double pow=1.0;
   for(i=1;i<=n;i++)
      pow=pow*base;
   return pow;
}
```
