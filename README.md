# 20190103 結構體
```
#include <stdlib.h>
int main(void)
{
   struct data		/* 定義結構data */
   {
      char name[10];
      int math;
   } student; 		/* 宣告data型態的結構變數student */
   
   printf("請輸入姓名: "); 
   _________(student.name);    			/* 輸入學生姓名 */
   
   printf("請輸入成績 :"); 
   scanf("%d",___________);  	/* 輸入學生成績 */
     
   printf("你輸入的學生姓名為':%s\n", ___________); 
   printf("該學生的成績為:%d\n", ____________); 
   
   system("pause");
   return 0;
}
```
# 20190103 指標練習

```
/* prog10_7, 傳遞指標到函數裡 */
#include <stdio.h>
#include <stdlib.h>
void address(int *);      /* 宣告address()函數的原型 */
int main(void)
{
   int a=12; 			/* 設定變數a的值為12 */
   int *ptr=&a; 			/* 將指標ptr指向變數a */
   
   address(&a);			/* 將a的位址傳入address()函數中 */
   address(ptr); 		/* 將ptr傳入address()函數中 */ 
   printf("最後a儲存的值(value)為%d\n",a);
   system("pause");
   return 0;
}
void address(int *p1)
{
   printf("於位址%p內，儲存的變數內容為%d\n",p1,*p1);
   *p1=*p1+5;
}
```
### 極重要觀念題:舉例說明call by address 與call by value的差異
```
以兩個整數變數的value互換為例:int a=20,b=19===>函式執行後(swap()互換)===>答案變成a=19,b=20

特別注意事項:
(1)函式宣告的形式
(2)函式本體的運算
```
call by value
```
/* prog10_9 */
#include <stdio.h> 
#include <stdlib.h>

void swap(______,_______);	

int main(void)
{
   int a=5,b=20;
   
   printf("... ");
   printf("a=%d,b=%d\n",a,b);
   
   swap(____,______);		
   
   printf("... ");
   printf("a=%d,b=%d\n",a,b);
   
   system("pause");
   return 0;
}

/* wap() */
void swap(int x,int y)	
{
   int _________;
   ________;
   ________;
}

```
call by address
```
/* prog10_10  */
#include <stdio.h> 
#include <stdlib.h>

void swap(_______,_______);  

int main(void)
{
   int a=5,b=20;
   
   printf("... ");
   printf("a=%d,b=%d\n",a,b);
   
   swap(______,_______);     
   
   printf("... ");
   printf("a=%d,b=%d\n",a,b);

   system("pause");
   return 0;
}

void swap(_______,_______)
{
   int _________;
   ________;
   ________;
}
```

### 極重要應用題:在C語言程式設計中如何設計一個改變多個數值的函數 

```
INPUT輸入:兩個整數代表長與寬
OUTPUT輸出:面積area與周長peri
```
```
基本做法:
寫兩個函釋分別計算與回傳出面積area與周長peri
```
```
關鍵技術:只用一個函示
設計一個函示輸入長與寬與要計算的面積area與周長peri
   myWork(a,b,&area,&peri)
透過指標變數將計算後的結果存入題目要的面積area與周長peri

特別注意:
(1)myWork()函式宣告
(2)myWork()函式本體的運算
```
```
/* prog10_11, 傳回多個數值的函數 */
#include <stdio.h> 
#include <stdlib.h>

void myWork(int,int,int *,int *);	/* 函數myWork()的原型 */

int main(void)
{
   int a=5,b=8;
   int area,peri;
   
   myWork(a,b,&area,&peri);  		/* 呼叫myWork(),計算面積及周長 */
   printf("area=%d,total length=%d\n",area,peri);

   system("pause");
   return 0;
}

void myWork(int x,int y,int *p1, int *p2)
{
   *p1=x*y;
   *p2=2*(x+y);
}
```

```
再增加計算三角形面積
```
### 練習題
```
INPUT輸入:代表角度的double雙精準浮點數變數THETA
OUTPUT輸出:sin(THETA),cos(THETA),tan(THETA),cot(THETA),sec(THETA)csc(THETA)
關鍵技術:只能使用一個函數

https://zh.wikipedia.org/wiki/Math.h
```
###  回傳address(位址)的函式設計技術
```
每一個函式透過return可以回傳一個(也只有一個)值/答案===>其實函式也可以回傳一個address(位址)===>這有甚麼用處????
```

```
INPUT輸入:三個正整數
OUTPUT輸出:三個正整數中最大值(MAX)
關鍵技術:
(1)使用一個函數int MAX()
(2)使用一個回傳address的函數int *MAX()
```
```
/* prog10_12, 由函數傳回指標  */
#include <stdio.h>
#include <stdlib.h>

int *max(int *,int *);		/* 宣告函數max()的原型 */

int main(void)
{
   int a=12,b=17,*ptr;

   ptr=max(&a,&b);

   printf("max=%d\n",*ptr);
   
   system("pause");
   return 0;
}

int *max(int *p1, int *p2)
{
   if(*p1>*p2)
      return p1;
   else 
      return p2;
}
```

# 20181227 指標練習

```
使用下列三種方式存取陣列的元素
[1]使用index存取
[2]使用pointer(指標變數)存取:陣列名稱==>pointer(指標變數
[3]使用pointer(指標變數)存取:利用一個pointer(指標變數)ptr指向陣列在移動指標去存取元素

計算一維陣列內所有元素的和 int a[5]={11,22,33,44,55};
取出最大元素
取出最小元素

將每一個陣列元素都加60
將每一個元素都依照位置(i)加上某一值(i+1)*5 ===>a[5]={11+5,22+10,33+15,44+20,55+25}
```
