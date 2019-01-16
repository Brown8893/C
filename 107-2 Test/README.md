
# 20190110 指向結構體的指標:Linked list

# 20190110 結構體陣列:每一個陣列元素都是結構體
```
宣告一個結構體student
其成員包括
一個字串代表其英文性名(不能超過10個字)
一個學號(如18080001,資料型態為整數)
一個程式設計成績(prog,資料型態為整數)

利用student結構體建立兩筆學生資料
trump  18080001  79
Obama  18080001  78

程式需再螢幕顯示出下列兩型資料

學號18080001的trump同學程式設計成績是79
學號18080002的Obama同學程式設計成績是78
```

```
/* prog11_7, 結構陣列的使用 */
#include <stdio.h>
#include <stdlib.h>
#define MAX 2
int main(void)
{
   int i;
   struct data			/* 定義結構data */
   {
      char name[10];
      int math;
   } student[MAX];		/* 宣告結構陣列student */
   
   for(i=0;i<MAX;i++)	 
   {
      printf("學生姓名: ");
      gets(student[i].name);			/* 輸入學生姓名 */
      printf("數學成績: ");
      scanf("%d",&student[i].math);		/* 輸入學生數學成績 */
      fflush(stdin);            			/* 清空緩衝區內的資料 */
   }

   for(i=0;i<MAX;i++)					/* 輸出結構陣列的內容 */
      printf("%s的數學成績=%d\n",student[i].name,student[i].math);
   
   system("pause");
   return 0;
}
```
```
/* prog11_6, 結構陣列的大小 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   struct student		/* 定義結構 */
   {
       char name[10];
       int KSUID;
       int program;
   }s[1];
   int i=0;
  for(i=0;i<=1;i++)
  {
  printf("PUT 姓名:");
  gets(s[i].name);
  printf("PUT KSUID:");
  scanf("%d",&s[i].KSUID);
  printf("PUT program:");
  scanf("%d",&s[i].program);
  fflush(stdin);
  printf("\n");
  printf("\n");
  printf("\n");
  }
  
  for(i=0;i<=1;i++)
  printf("學號%d的%s同學程式設計成績是%d\n",s[i].KSUID,s[i].name,s[i].program);
  
   
   
   printf("sizeof(student[3])=%d\n",sizeof(s[3]));
   printf("sizeof(student)=%d\n",sizeof(s));
   system("pause");
   return 0;
}
```
```
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
	struct student /*結構設定*/
	{
		char name[10];
		int ID;
		int prog;
	 } 
	 
	 struct student s[2];
	 s[0].name[10]="trump";
         s[0].ID=18080001;
	 s[0].prog=79;
	 s[1].name[10]="Obama";
         s[1].ID=18080002;
	 s[1].prog=78;
	 
	 printf("學號%d的%s同學的程式設計成績是%d\n",s[0].ID,s[0].name,s[0].prog);
	 printf("學號%d的%s同學的程式設計成績是%d\n",s[1].ID,s[1].name,s[1].prog);
	 
	 system("pause");
	 return 0;
}
```

```
/* prog11_4, 結構的設值 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   struct data
   {
      char name[10];
      int num;
	  int math;
   } s1={"trump",18080001,83},s2={"Obama",18080002,84};   	/* 宣告結構變數s1，並設定初值 */
  		/* 宣告結構變數s2 */
   
   printf("s1.name=%s,s1.num=%d,s1.math=%d\n",s1.name,s1.num,s1.math);
   printf("s2.name=%s,s2.num=%d,s2.math=%d\n",s2.name,s2.num,s2.math);
   
   system("pause");
   return 0;
}
```
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
[2]使用pointer(指標變數)存取:陣列名稱==>pointer(指標變數)
[3]使用pointer(指標變數)存取:利用一個pointer(指標變數)ptr指向陣列,再移動指標去存取元素(value)

計算一維陣列內所有元素的和 int a[5]={11,22,33,44,55};
取出最大元素
取出最小元素

將每一個陣列元素都加60
將每一個元素都依照位置(i)加上某一值(i+1)*5 ===>a[5]={11+5,22+10,33+15,44+20,55+25}
```
# 20181227 陣列練習

### 一維陣列的基本操作score[4]={99,11,23,44}:完成底下填充[prog9_1.c]
```
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   /* 宣告整數變數i當作index與整數陣列score */
   int i,score[4]; 	
   
   /* 設定陣列的內容  */   
   score[0]=___;		
   ___________; 	
   ___________;   	
   ___________; 		
   
   /* 使用一個for loop將陣列的內容一一印出  */
   for(i=0;i<=3;i++)
      printf("score[%d]=___\n",i,_______); 
   
   system("pause");
   return 0;
}
```
### 說明底下程式有哪些錯誤:一維陣列的基本操作[prog9_2]
```
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int i,score[4]; 
   
   score[0]=118;		
   score[1]=552; 		
   score[3]=809; 		
   
   for(i=0;i<=5;i++)	
      printf("score[%d]=%d\n",i,score[i]);  
   
   system("pause");
   return 0;
}
```
###
```
```
###
```
/* prog9_3, 查詢陣列所佔的記憶空間 */ 
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   double data[4];	/* 宣告有4個元素的double型態陣列 */
   printf("陣列元素所佔的位元組:%d\n",sizeof(data[0]));
   printf("整個陣列所佔的位元組:%d\n",sizeof(data));
   printf("陣列元素的個數:%d\n",sizeof(data)/sizeof(double));
   
   system("pause");
   return 0;
}
```
###
```
/* prog9_4, 一維陣列內元素的設值 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int i,age[3];
   for(i=0;i<3;i++)
   {
      printf("請輸入age[%d]的值:",i);
      scanf("%d",&age[i]);	  /* 由鍵盤輸入數值給陣列age裡的元素 */
   }
   for(i=0;i<3;i++)
      printf("age[%d]=%d\n",i,age[i]);

   system("pause");
   return 0;
}
```
###
```
/* prog9_5, 比較陣列元素值的大小 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int A[5]={74,48,30,17,62};
   int i,min,max;
   min=max=A[0];		/* 將max與min均設為陣列的第一個元素 */
   
   for(i=0;i<5;i++)
   {
      if(A[i]>max) 	/* 判斷A[i]是否大於max */
         max=A[i];	
      if(A[i]<min) 	/* 判斷A[i]是否小於min */
         min=A[i];	
   }
   printf("陣列裡元素的最大值為%d\n",max);
   printf("陣列裡元素的最小值為%d\n",min);
   
   system("pause");
   return 0;
}


```
###
```
/* prog9_6, 輸入未定個數的資料到陣列裡 */
#include <stdio.h>
#include <stdlib.h>
#define MAX 10		/* 定義MAX為10 */
int main(void)
{
   int score[MAX];	/* 宣告有10個元素的整數陣列 */
   int i=0,num;
   int sum=0;		/* 宣告用來成績總和的變數sum */
	
   printf("請輸入成績，要結束請輸入0:\n");
   do 
   {
      printf("請輸入成績:");
      scanf("%d",&score[i]);
   }while(score[i++]>0);  		/* 輸入成績，輸入0時結束 */
   num=i-1;
   for(i=0;i<num;i++)
      sum+=score[i];				/* 計算平均成績 */
   printf("平均成績為 %.2f\n",(float)sum/num);
   system("pause");
   return 0;
}
```

###
```
/* prog9_7, 陣列的界限檢查 */
#include <stdio.h>
#include <stdlib.h>
#define MAX 5		/* 定義MAX為5 */
int main(void)
{
   int score[MAX]; 	/* 宣告score陣列，可存放MAX個整數 */
   int i=0,num;
   float sum=0.0f;
   
   printf("請輸入成績，要結束請輸入0:\n");
   do
   {
      if(i==MAX)		/* 當i的值為MAX時，表示陣列已滿，即停止輸入 */
      {
         printf("陣列空間已使用完畢!!\n"); 
         i++;			/* 此行先將i值加1，因為23行會把i的值減1掉 */
         break;
      }
      printf("請輸入成績:");
      scanf("%d",&score[i]);
   }while(score[i++]>0);   /* 輸入成績，輸入0時結束 */
   num=i-1;
   for(i=0;i<num;i++)
      sum+=score[i];		/* 計算平均成績 */
   printf("平均成績為 %.2f\n",sum/num);
   
   system("pause");
   return 0;
}
```
### 循序搜尋演算法[prog9_8 陣列的搜尋]
```
搜尋演算法有許多類型:
Linear Search循序搜尋
Binary Search
Jump Search
Interpolation Search
Exponential Search
Sublist Search (Search a linked list in another list)
Fibonacci Search
The Ubiquitous Binary Search
Recursive program to linearly search an element in a given array
Recursive function to do substring search
Unbounded Binary Search Example (Find the point where a monotonically increasing function becomes positive first time)
https://www.geeksforgeeks.org/searching-algorithms/
https://en.wikipedia.org/wiki/Search_algorithm
```
```
#include <stdio.h>
#include <stdlib.h>
#define SIZE 6		/* 定義SIZE為6 */
int main(void)
{
   int i,num,flag=0;
   int A[SIZE]={33,75,69,41,33,19};
		
   printf("陣列A元素的值為:");
   for(i=0;i<SIZE;i++)			
      printf("%d ",A[i]); 			/* 印出陣列的內容 */
   
   printf("\n請輸入欲搜尋的整數:");		
   scanf("%d",&num); 				/* 輸入欲搜尋的整數 */
   
   for(i=0;i<SIZE;i++)
      if(A[i]==num)	/* 判斷陣列元素是否與輸入值相同 */
      {
         printf("找到了! A[%d]=%d\n",i,A[i]);
         flag=1;		/* 設flag為1，代表有找到相同的數值 */
      }
   if(flag==0)
      printf("沒有找到相同值!!\n");
   
   system("pause");
   return 0;
}
```
###
```
/* prog9_9, 二維陣列的輸入輸出 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int i,j,sale[2][4],sum=0;
		
   for(i=0;i<2;i++)
      for(j=0;j<4;j++)
      {
         printf("業務員%d的第%d季業績:",i+1,j+1);
         scanf("%d",&sale[i][j]); 		/* 輸入銷售量 */
      }
   
   printf("***Output***");
   for(i=0;i<2;i++)				/* 輸出銷售量並計算總銷售量 */
   {
      printf("\n業務員%d的業績分別為",i+1);
      for(j=0;j<4;j++)
      {
         printf("%d  ",sale[i][j]);
         sum+=sale[i][j];
      }
   }
   printf("\n2004年總銷售量為%d部車\n",sum);
   
   system("pause");
   return 0;
}
```
### 二維陣列及其運算:prog9_10, 矩陣的相加
```
#include <stdio.h>
#include <stdlib.h>
#define ROW 2		/* 定義ROW為2 */
#define COL 3		/* 定義COL為3 */
int main(void)
{
   int i,j;
   int A[ROW][COL]={{1,2,3},{5,6,8}};	/* 宣告陣列A並設定初值 */
   int B[ROW][COL]={{3,0,2},{3,5,7}};  	/* 宣告陣列B並設定初值 */ 
	
   printf("Matrix A+B=\n");
   for(i=0;i<ROW;i++)			/* 外層迴圈，用來控制列數 */
   {
      for(j=0;j<COL;j++)		/* 內層迴圈，用來控制行數 */
         printf("%3d",A[i][j]+B[i][j]); 		/* 計算二陣列相加 */
      printf("\n");
   }
   system("pause");
   return 0;
}
```
### 三維陣列及其運算
```
/* prog9_11, 三維陣列與初值的設定 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int A[2][4][3]={{{21,32,65},
                     	{78,94,76},
                    	{79,44,65},
                    	{89,54,73}},
                   	  {{32,56,89},
                    	{43,23,32},
                    	{32,56,78},
                    	{94,78,45}}};
   
   int i,j,k,max=A[0][0][0];	/* 設定max為A陣列的第一個元素 */
		
   for(i=0;i<2;i++)	   		/* 外層迴圈 */
      for(j=0;j<4;j++)		/* 中層迴圈 */
         for(k=0;k<3;k++)		/* 內層迴圈 */
            if(max<A[i][j][k])
                max=A[i][j][k];
   
   printf("max=%d\n",max);	/* 印出陣列的最大值 */
   system("pause");
   return 0;
}
```
### 函數的參數傳遞:Call by value vs Call by address
```
/* prog9_12, 傳遞一維陣列到函數裡 */
#include <stdio.h>
#include <stdlib.h>
#define SIZE 4
void show(int arr[]);		/* 宣告函數show()的原型 */

int main(void)	
{
   int A[SIZE]={5,3,6,1};		/* 設定陣列A的初值 */

   printf("陣列的內容為: ");   
   
   show(A);					
   /* 呼叫函數show:將(A陣列的位址當作參數傳遞給show函數) */

   system("pause");
   return 0;
}

/* 定義show()函數 */
void show(int arr[])			
{
   int i;
   for(i=0;i<SIZE;i++)		
      printf("%d ",arr[i]); 	/* 印出陣列內容 */
   printf("\n");
}
```
### prog9_13, 變數的位址(address)與值(value)
```
/*  */
#include <stdio.h>
#include <stdlib.h>
void func(int);
int main(void)
{
   int a=13;
   printf("於main()裡,a=%d,a的位址=%p\n",a,&a);
   func(a);			/* 這是傳值呼叫的機制 */
   
   system("pause");
   return 0;
}

void func(int a)		/* 自訂函數func() */
{	
   printf("於func()裡,a=%d,a的位址為=%p\n",a,&a);
}
```
### prog9_14, 印出陣列的位址
```
#include <stdio.h>
#include <stdlib.h>
#define SIZE 3	
void func(int arr[]);
int main(void)
{
   int i,A[SIZE]={20,8,13};

   printf("在main()裡，陣列A元素的位址為\n"); 
   for(i=0;i<SIZE;i++)
      printf("A[%d]=%2d,位址為%p\n",i,A[i],&A[i]);
   func(A);				/* 這是傳址呼叫的機制 */
   
   system("pause");
   return 0;
}

void func(int arr[])		/* 自訂函數func() */
{	
   int i;
   printf("\n在func()裡，陣列arr元素的位址為\n");
   for(i=0;i<SIZE;i++)
      printf("arr[%d]=%2d,位址為%p\n",i,arr[i],&arr[i]);
}
```
### prog9_15, 印出陣列的位址
```
#include <stdio.h>
#include <stdlib.h>
#define SIZE 3
int main(void)
{
   int i,A[SIZE]={20,8,13};

   for(i=0;i<SIZE;i++)
      printf("A[%d]=%2d,位址為%p\n",i,A[i],&A[i]);
   printf("陣列A的位址=%p\n",A);    /* 印出陣列A的位址 */
   
   system("pause");
   return 0;
}
```
### prog9_16
```

```
### 氣泡排序法
```
prog9_17, 氣泡排序法
prog9_18, 氣泡排序法之改良版

```
## 字串==字元陣列
## 字串處理的各種練習
### prog9_19
```

```
###
```
/* prog9_20, 印出字元及字串的長度 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   char ch='a';				/* 宣告字元變數ch */
   char str1[]="a";			/* 宣告字串變數str1 */
   char str2[]="Sweet home";	/* 宣告字串變數str2 */   

   printf("字元ch佔了%d個位元組\n",sizeof(ch));
   printf("字串str1佔了%d個位元組\n",sizeof(str1));
   printf("字串str2佔了%d個位元組\n",sizeof(str2));
 
   system("pause");
   return 0;
}
```

###
```
/* prog9_21, 輸入及印出字串 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   char name[15];	/* 宣告字元陣列name */
		
   puts("What's your name?");
   gets(name);		/* 利用gets()讀入字串，並寫入字元陣列name裡 */
   puts("Hi!");
   puts(name);		/* 印出字元陣列name的內容 */
   puts("How are you?");
   system("pause");
   return 0;
}
```

### 字串處理[prog9_22, 將字串裡小寫字母轉換成大寫]
```
#include <stdio.h>
#include <stdlib.h>
void toUpper(char s[]);	/* 宣告函數toUpper()的原型 */

int main(void)
{
   char str[15];			/* 宣告可容納15個字元的陣列str */
		
   printf("請輸入一個字串: ");
   gets(str);			/* 輸入字串 */
   toUpper(str);			/* 呼叫toUpper() 函數 */
   printf("轉換成大寫後: %s\n",str);		/* 印出str字串的內容 */
   
   system("pause");
   return 0;
}

/* toUpper() 函數核心內容 */
void toUpper(char s[])
{
   int i=0;
   while(s[i]!='\0')		/* 如果s[i] 不等於\0，則執行下面的敘述 */
   {
      if(s[i]>=97 && s[i]<=122) /* 如果是小寫字母 */
         s[i]=s[i]-32;		/* 把小寫字母的ASCII碼減32，變成大寫 */
      i++;
   }
}
```
### 字串處理[將字串裡大寫字母轉換成小寫]
```
#include <stdio.h>
#include <stdlib.h>
void toLower(char s[]);	/* 宣告函數toLower()的原型 */

int main(void)
{
   char str[15];			/* 宣告可容納15個字元的陣列str */
		
   printf("請輸入一個字串: ");
   gets(str);			/* 輸入字串 */
   toLower(str);			/* 呼叫toLower() 函數 */
   printf("轉換成大寫後: %s\n",str);		
   
   system("pause");
   return 0;
}

/* toLower() 函數核心內容 */
void toLower(char s[])
{
   填入你的程式碼......
   }
}
```
### 字串反轉
```

```
## 字串陣列==陣列元素都是存字串

### 字串陣列[prog9_23]
```
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   char S[3][10]= {"Tom","Lily","James Lee"};
   int i;
   
   /* 使用for loop一一印出字串陣列內容 */
   for(i=0;i<3;i++)		
      printf("S[%d]=%s\n",i,S[i]);    
      
   printf("\n");
   
   /* 使用for loop一一印出字串陣列元素的內容(value)與位址(address)*/
   for(i=0;i<3;i++)	
   {
      /* 印出字串元素的內容(value) */
      printf("S[%d]=____\n",i,______);
      
      /* 印出字串元素的位址*/    
      printf("address of S[%d][0]=________\n\n",i,_______);
   }
   
   system("pause");
   return 0;
}
```
### 字串陣列的複製[prog9_24]
```
#include <stdio.h>
#include <stdlib.h>
#define MAX 3
#define LENGTH 10
int main(void)
{
   char arr1[MAX][LENGTH]={"Tom","Lily","James Lee"};
   char arr2[MAX][LENGTH];
   int i,j;
   
   /* 使用兩層loop(i,j)將arr1的內容複製到arr2中 */
   for(i=0;i<MAX;i++) 	
   {
      for(j=0;j<LENGTH;j++)
         if(arr1[i][j]=='\0')   /* 如果遇到「\0」,代表讀到字串結束==>要如何處理呀? */
            _______;		  		
         else
            arr2[i][j]=arr1[i][j];
            
        ______________;      /* 最後新陣列要補上「\0」字串結束 */
   }
   
   /* 使用 for loop 印出陣列arr2的內容 */
   for(i=0;i<MAX;i++) 	
      printf("arr2[%d]=%s\n",i,arr2[i]);  
   
   system("pause");
   return 0;
}
```
### 字串陣列的反轉

```
input輸入:char arr1[MAX][LENGTH]={"Tom","Lily","James Lee"};
output輸出:char arr2[MAX][LENGTH]={"m0T","yliL","eeL semaJ"};
```
### 字串陣列的大寫化
### 字串陣列的小寫化


# 20181220練習
```
[1]完成底下網址的51題練習[要交簡報]
https://www.w3schools.com/python/python_exercises.asp

[2]完成C語言指標作業

```

```
指標變數與一維陣列的存取
指向指標的指標 與二維陣列的存取
指標陣列 
```
# 20181213:超難的指標一定要會

### ex-1:
```
/* prog10_2, 指標變數的宣告 */
#include <stdio.h> 
#include <stdlib.h>
int main(void)
{
   int *ptr,d=100,num=20,c=33;	/* 宣告變數num與指標變數ptr */

   ptr=&num;			/* 將num的位址設給指標ptr存放 */
   printf("num=%d, &num=%p\n",num,&num); 
   printf("*ptr=%d, ptr=%p, &ptr=%p\n",*ptr,ptr,&ptr); 
   printf("c=%d, c的位址=%p\n",c,&c); 
   printf("d=%d, d的位址=%p\n",d,&d); 
   system("pause");
   return 0;
}
```
```
假如 c存放的位址是000000000062FE3C
請問你 
[1]d的位址為何?
[2]num的位址為何?
[3]ptr的位址為何?
```
### ex-2:
```
#include <stdio.h> 
#include <stdlib.h>
int main(void)
{
   int *ptr,d=103,num=210,c=333;	

   ptr=&num;			
   printf("num=%d, num的位址=&num=%p\n",num,&num); 
   printf("*ptr=%d, ptr=%p, &ptr=%p\n",*ptr,ptr,&ptr); 
   ptr=&c;
   printf("c=%d, c的位址=&c=%p\n",c,&c); 
   printf("*ptr=%d, ptr=%p, &ptr=%p\n",*ptr,ptr,&ptr); 
   ptr=&d;
   printf("d=%d, d的位址=&d=%p\n",d,&d); 
   printf("*ptr=%d, ptr=%p, &ptr=%p\n",*ptr,ptr,&ptr);  
   system("pause");
   return 0;
}

```
```
假如 c存放的位址是000000000062FE3C
請問你 
[1]
   ptr=&num;			
   printf("num=%d, num的位址=&num=%p\n",num,&num); --->印出的內容為何??
   printf("*ptr=%d, ptr=%p, &ptr=%p\n",*ptr,ptr,&ptr); --->印出的內容為何??
[2]
   ptr=&c;
   printf("c=%d, c的位址=&c=%p\n",c,&c); --->印出的內容為何??
   printf("*ptr=%d, ptr=%p, &ptr=%p\n",*ptr,ptr,&ptr); --->印出的內容為何??
[3]
   ptr=&d;
   printf("d=%d, d的位址=&d=%p\n",d,&d); --->印出的內容為何??
   printf("*ptr=%d, ptr=%p, &ptr=%p\n",*ptr,ptr,&ptr);  --->印出的內容為何??

```

### 練習1:完成底下的填空題

```
#include <stdio.h> 
#include <stdlib.h>
int main(void)
{

/*1:宣告一個整數變數,名稱叫myint出值設定為30 */

   int ________=________;
   
/*2:宣告一個指向整數的指標變數,名稱叫myptr */
   int _________;	

/* 3:將myint的位址存在myptr指標變數 */
   _______=_____;		
   
/* 4.印出myint的位址與所儲存的值 */
   printf("myint整數變數值=________, "myint的位址=&myint=_______\n",_______,______);

/* 5.印出myptr的位址與所儲存的值及*ptr的值 */
   printf("*myptr=______, myptr=________, &myptr=_________\n",________,_________,__________); 
   system("pause");
   return 0;
}

```

### ex-3:10_5.c程式設計

針對底下程式逐行說明執行成果

```
/* prog10_5, 指標的操作練習 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int a=56,b=101;
   int *ptr1,*ptr2;
   ptr1=&a;				
   ptr2=&b;			 	
   *ptr1=22;			 	
   *ptr2=42;				
   a=57;			 
   ptr1=ptr2;		 	
   *ptr1=22;		 	 	
   ptr1=&a;		 	 
   a=34;            		
   *ptr2=*ptr1+9; 	
   ptr2=&a;		 		
   
   printf("a=%2d, b=%2d, *ptr1=%2d, *ptr2=%2d\n",a,b,*ptr1,*ptr2);
   printf("ptr1=%p, ptr2=%p\n",ptr1,ptr2);   
   printf("ptr1=%p, ptr2=%p\n",&ptr1,&ptr2);    
   system("pause");
   return 0;
}

```

作答
```
/* prog10_5, 指標的操作練習 */
#include <stdio.h>
#include <stdlib.h>
int main(void)
{
   int a=56,b=101;
   int *ptr1,*ptr2;
   ptr1=&a;			------> ptr1變數存放的內容是__________________	
   ptr2=&b;			------> ptr2變數存放的內容是__________________	 	
   *ptr1=22;		------> a的值是多少________  	的值是多少________  	
   *ptr2=42;		------> a的值是多少________  	的值是多少________  			
   a=57;			   ------> a的值是多少________  	的值是多少________  	
   ptr1=ptr2;		------> ptr1變數存放的內容是__________________	     ptr2變數存放的內容是__________________ 	
   *ptr1=22;		------> a的值是多少________  	的值是多少________  	 	 	
   ptr1=&a;		 	------> ptr1變數存放的內容是__________________	     ptr2變數存放的內容是__________________  
   a=34;          ------> a的值是多少________  	的值是多少________   		
   *ptr2=*ptr1+9; ------> a的值是多少________  	的值是多少________ 	
   ptr2=&a;		 	------> ptr1變數存放的內容是__________________	     ptr2變數存放的內容是__________________ 	
   
   printf("a=%2d, b=%2d, *ptr1=%2d, *ptr2=%2d\n",a,b,*ptr1,*ptr2);------>這行在印甚麼?
   printf("ptr1=%p, ptr2=%p\n",ptr1,ptr2);   ------>這行在印甚麼?
   printf("ptr1=%p, ptr2=%p\n",&ptr1,&ptr2);  ------>這行在印甚麼?
   system("pause");
   return 0;
}

```

# 20181018作業
```
完成Python教科書Ch 1.9的閱讀與練習
完成Python教科書Ch 1作業:十題以上(放在你的github)
```
```
完成Python教科書Ch 2作業:2.1+2.5(放在你的github)
ex2.2
ex2.11
ex2.18
完成Python教科書Ch 2作業:2.5+2.6+2.7+2.21(放在你的github)
```
```
完成Python教科書Ch 3作業:3.8-3.11(放在你的github)
```
# C
```
runoob
```

# 參考書
```
C語言教學手冊（四版）（附1光碟）
作者： 洪維恩  
出版社：旗標 
https://www.books.com.tw/products/0010360466
```
```
Python程式設計入門指南
Introduction to Programming Using Python
作者： Y. Daniel Liang  

譯者： 蔡明志
出版社：碁峰 
https://www.books.com.tw/products/0010719771
```
# C 程式設計入門
```
參考書
實用 C 語言程式設計入門
作者： 施威銘研究室  
出版社：旗標  
出版日期：2018/06/15

第 1 章 認識 C 語言
1-1 本章簡介
1-2 上機實作：與 C 語言的第一次接觸
1-2-1 接觸 C 語言：從零開始
1-2-2 輸出第一行字

1-3 C 語言的基本輸出入和程式架構
1-3-1 main(void) 是什麼意思
1-3-2 標頭檔 #include <...> 淺說
1-3-3 程式的分段：使用大括號 {} 與分號

1-4 程式的註解與編排
1-4-1 適時的分行：便於整篇程式的閱讀
1-4-2 程式碼內縮：表現出程式的層次感
1-4-3 善用註解：幫助了解程式
1-4-4 使用區塊註解
1-5 如何讓 C 語言程式變成可以執行

第 2 章 常數與變數
2-1 本章簡介
2-2 定義常數
2-2-1 用 #define 定義常數
2-2-2 定義常數不可更改其值

2-3 變數的資料型別
2-3-1 資料型別的類型與長度
2-3-2 資料型別的修飾字
2-3-3 數值發生溢位的情況

2-4 變數命名的原則與習慣
2-4-1 變數命名的合法性
2-4-2 變數命名的習慣

2-5 宣告變數
2-5-1 宣告變數的語法
2-5-2 宣告變數的位置
2-5-3 指定變數的值
2-5-4 兩個變數的值互相交換
2-5-5 宣告變數的修飾詞 - const

2-6 變數的資料型別轉換
2-6-1 整數轉成浮點數
2-6-2 浮點數轉成整數
2-6-3 字元和數字間的轉換
2-6-4 大寫字母轉成小寫字母

第 3 章 基本輸出與輸入函式
3-1 本章簡介

3-2 格式化輸出
3-2-1 以不同進位制控制符號顯示
3-2-2 以科學符號表示法顯示

3-3 輸出格式可用的參數
3-3-1 指定輸出的固定寬度
3-3-2 指定輸出寬度時加上正負符號
3-3-3 讓輸出的數值向左靠齊
3-3-4 組合多個參數輸出

3-4 使用跳脫序列控制輸出
3-4-1 刪除、歸位、跳格跳脫序列
3-4-2 輸出單、雙引號與反斜線的跳脫序列
3-4-3 輸出到此為止的結束跳脫序列

3-5 輸入與輸出單一字元的函式
3-5-1 輸入、輸出字元：getchar()、putchar() 函式
3-5-2 不用按Enter 鍵輸入字元：getche()、getch() 函式

3-6 使用輸入數值函式scanf()
3-6-1 scanf() 函式的用法
3-6-2 輸入的數值與指定的格式要相符
3-6-3 避免讀入Tab、Space、Enter 鍵

第 4 章 運算子、運算元與算式
4-1 本章簡介
4-2 算式的結構

4-3 運算子的優先權
4-3-1 運算子與運算元結合的優先權
4-3-2 運算子優先權相同時的結合性順序

4-4 算術運算子
4-5 括號運算子
4-6 關係運算子
4-7 邏輯運算子
4-8 指定運算子與複合指定運算子
4-9 遞增與遞減運算子

4-10 綜合練習
4-10-1 溫度轉換：攝氏轉華氏
4-10-2 遊樂場換幣機程式
4-10-3 判斷輸入的是否為英文字母
4-10-4 計算整數的階乘

第 5 章 條件判斷式
5-1 本章簡介
5-2 if 條件判斷
5-3 if-else 條件判斷
5-4 if-else if 條件判斷
5-5 if 巢狀條件判斷
5-6 switch-case 條件判斷
5-7 三運算元條件判斷式 ?：

5-8 綜合練習
5-8-1 將Ch05_07.c 改用「switch-case」與「? :」取代
5-8-2 輸入月份與日期，用if-else 與switch-case 查星座
5-8-3 用if-else 與 ? : 將輸入的3 個數字做大小排序

第 6 章 迴圈控制
6-1 本章簡介

6-2 執行指定次數的for 迴圈
6-2-1 改變控制算式的遞增量或遞減量
6-2-2 for 迴圈允許超過一組算式
6-2-3 巢狀for 迴圈

6-3 預先判斷是否執行的while 迴圈
6-3-1 利用while 迴圈猜數字
6-3-2 利用while 迴圈算最大公因數

6-4 後設條件判斷的do-while 迴圈

6-5 無限迴圈
6-5-1 for 無限迴圈的用法
6-5-2 while 無限迴圈的用法

6-6 直接跳出迴圈的break、continue 與goto
6-6-1 跳出一層迴圈可使用break
6-6-2 立刻跳到迴圈開頭的continue
6-6-3 強迫跳到指定標籤名的goto

6-7 綜合練習
6-7-1 輸出英文字母金字塔
6-7-2 找出2~200 之間的所有質數
6-7-3 計算指定正整數的階乘

第 7 章 自訂函式
7-1 本章簡介
7-2 宣告函式的寫法與位置

7-3 定義自訂函式
7-3-1 計算絕對值的自訂函式
7-3-2 計算BMI 的自訂函式
7-3-3 找出質數的自訂函式
7-3-4 計算幾次方的自訂函式
7-3-5 計算度量衡轉換的自訂函式
7-3-6 從自訂函式呼叫另一個自訂函式

7-4 遞迴函式
7-4-1 跌入萬丈深淵的無窮遞迴
7-4-2 利用遞迴算最大公因數
7-4-3 利用遞迴算因數分解
7-4-4 利用遞迴算費氏數列
7-4-5 利用遞迴算正整數的階乘
7-4-6 利用遞迴搬河內塔圓盤

第 8 章 巨集
8-1 本章簡介
8-2 定義巨集與放的位置
8-3 無引數的巨集取代算式
8-4 有引數的巨集取代算式
8-5 多個引數的巨集與條件判斷的巨集
8-6 將算式做為巨集的引數

第 9 章 前置處理
9-1 本章簡介
9-2 將標頭檔含括進程式
9-2-1 內建的標頭檔
9-2-2 自己寫的標頭檔
9-3 條件編譯
9-3-1 條件編譯指令 #ifndef、#endif 的用法
9-3-2 條件編譯指令 #ifdef、#else、#endif 的用法
9-3-3 條件編譯指令 #if、#elif、#endif 的用法

第 10 章 陣列
10-1 本章簡介
10-2 一維陣列
10-2-1 宣告一維陣列
10-2-2 宣告陣列時設定初值與改變初值
10-2-3 執行過程指定陣列的數值
10-3 二維陣列
10-3-1 指定二維陣列的初值
10-3-2 執行過程指定二維陣列的數值
10-4 多維陣列
10-5 陣列在函式間的傳遞
10-5-1 傳遞一維陣列
10-5-2 傳遞二維陣列
10-5-3 傳遞陣列是傳遞記憶體位址

第 11 章 字串
11-1 本章簡介
11-2 字元陣列與字串的差異
11-3 宣告字串與設定初值
11-3-1 輸出字串要用%s 控制符號
11-3-2 用字元陣列的方式設定初值
11-4 由鍵盤讀取字串與從螢幕輸出字串
11-4-1 使用scanf() 讀取字串的方法
11-4-2 使用gets() 讀取字串，puts() 輸出字串
11-5 處理字串的函式
11-5-1 複製字串：strcpy() 函式
11-5-2 複製局部字串：strncpy() 函式
11-5-3 算出字串真正的長度：strlen() 函式
11-5-4 比對兩個字串是否完全相符：strcmp() 函式
11-5-5 比對兩字串前面部份是否相符：strncmp() 函式
11-5-6 完整串接兩個字串：strcat() 函式
11-5-7 串接指定字元的字串：strncat() 函式
11-6 字串陣列
11-6-1 輸出字串陣列的初值
11-6-2 讀取、比對字串陣列中的字串

第 12 章 指標
12-1 本章簡介
12-2 記憶體位址
12-3 指標的基本用法
12-3-1 指標佔的記憶體大小與位址
12-3-2 改變指標指向的數值
12-3-3 改變指標指向的變數
12-4 指標與陣列
12-4-1 用指標讀取字串
12-4-2 用指標讀取二維陣列
12-4-3 指標陣列：每個陣列元素都是指標
12-5 指標與函式
12-5-1 傳址呼叫
12-5-2 函式可以傳回指標位址
12-6 雙重指標（指向指標的指標）
12-7 指標與動態記憶體配置
12-8 未指定資料型別的void 指標
12-9 使用指標的好處

第 13 章 變數等級
13-1 本章簡介
13-2 變數的視野與生命期
13-3 內部變數
13-3-1 宣告內部變數，有無auto 都可以
13-3-2 內部變數生命期結束，就被釋放
13-4 外部變數
13-4-1 到處都可用到的外部變數
13-4-2 內部、外部變數名稱相同的優先順序
13-4-3 擴展外部變數視野的extern 用法
13-4-4 跨檔案取用外部變數的extern 用法
13-5 內部靜態變數與外部靜態變數
13-6 暫存器變數

第 14 章 檢驗輸入的資料
14-1 本章簡介
14-2 檢驗英文字母與數字
14-2-1 檢驗字元為英文字母與數字：isalnum() 函式
14-2-2 檢驗字元或數字：isalpha()、isdigit() 函式
14-3 檢驗 ASCII 字元
14-3-1 檢驗 ASCII 字元：isascii()、iscntrl()、isspace() 函式
14-3-2 檢驗大小寫英文字母：isupper()、islower() 函式
14-3-3 檢驗非英數字空格的可列印字元：ispunct() 函式

第 15 章 結構體、共用體、別名、列舉
15-1 本章簡介
15-2 結構體
15-2-1 宣告結構體變數與設定初值
15-2-2 宣告結構體同時宣告結構體變數
15-2-3 結構體中還可以有結構體成員
15-3 結構體變數陣列
15-4 將結構體宣告為指標變數
15-5 將結構體變數傳給函式
15-5-1 傳遞結構體引數的函式原型宣告
15-5-2 結構體變數的傳值呼叫
15-5-3 結構體變數的傳址呼叫
15-6 共用體
15-7 共用體與結構體組合使用
15-8 別名
15-9 列舉

第 16 章 檔案處理
16-1 本章簡介
16-2 檔案讀寫的觀念
16-3 開啟與關閉檔案
16-3-1 開啟檔案：fopen() 函式
16-3-2 關閉檔案：fclose() 函式
16-4 讀取檔案資料
16-4-1 讀取檔案的字元與字串：fgetc()、fgets() 函式
16-4-2 讀取格式化資料：fscanf() 函式
16-4-3 利用正規表示式處理逗點分隔的字串
16-5 寫入檔案資料
16-5-1 將字元與字串寫入檔案：fputc()、fputs() 函式
16-5-2 依格式寫入檔案：fprintf() 函式
16-6 隨機式檔案讀寫
16-6-1 找出指標位置與讓指標回到檔頭：ftell()、rewind() 函式
16-6-2 移動指標並讀取資料：fseek()、fread() 函式
16-6-3 將指定大小的資料寫入檔案：fwrite() 函式

附錄 A ASCII 碼表
附錄 B 使用 Dev-C++
B-1 下載與安裝 Dev-C++
B-2 執行範例程式
B-2-1 開啟 C 程式檔
B-2-2 編譯、連結、執行程式
B-2-3 單獨執行程式
B-3 在 Dev-C++ 中建立新程式檔
B-4 在 Dev-C++ 中建立新專案

附錄 C Dev-C++ 除錯功能
C-1 以逐步執行的方式觀察程式
C-1-1 建立中斷點
C-1-2 逐步執行程式
C-2 使用監看功能
C-2-1 新增監看式
C-2-2 檢視變數值
```
# Python
```
Python程式設計入門指南
Introduction to Programming Using Python
作者： Y. Daniel Liang  

譯者： 蔡明志
出版社：碁峰 
https://www.books.com.tw/products/0010719771
```

```
```
```
```
