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

```
