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

```
