# C-
C语言学习时留下的代码
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>
#include <string.h>                  //使用strlen函数需引用该头文件

////指针
//int main()
//{
//	printf("%d\n", sizeof(int*));
//	printf("%d\n", sizeof(short*));
//	printf("%d\n", sizeof(long*));
//	printf("%d\n", sizeof(long long*));
//	printf("%d\n", sizeof(float*));
//	printf("%d\n", sizeof(double*));             //指针大小在32位平台是4个字节，在64位平台是8个字节
//
//	return 0;
//}

//int main()
//{
//	int a = 0;
//	int *p = &a;       //取地址
//	*p = 20;           //* ——解引用操作符
//
//	//printf("%p\n", &a);  //指针变量——用来存放地址的变量
//	printf("%d\n", a);
//	return 0;
//}


////  宏的定义
////  定义标识符常量
////  #define Max 100
////  定义宏——带参数
////#define Max 100                 //将Max定义为100
//#define MAX(X,Y) (X>Y?X:Y)       //定义MAX函数 
//int main()
//{
//	int a = 0;
//	int b = 0;
//	scanf("%d%d", &a, &b);
//	int max = MAX(a, b);             //使用宏的方式
//	printf("%d\n", max);
//
//	return 0;
//}


//extern int Add(int, int);                //static  修饰函数             改变函数的链接属性      让函数的外部链接属性——>内部链接属性
//int main()
//{
//	int num1 = 0;
//	int num2 = 0;
//	scanf("%d%d", &num1, &num2);
//	int sum = Add(num1,num2);
//	printf("%d\n", sum);
//	return 0;
//}


//static 修饰的局部变量       将局部变量的生命周期延长
//       修饰去全局变量       改变全局变量的作用域   使其只能在其所在的源文件内使用
//       修饰函数             改变函数的链接属性      让函数的外部链接属性——>内部链接属性


//int main()
//{
//	//extern  声明外部符号的
//	extern int a;                 //若加上static修饰，则全局变量只能在其本身所在的源文件内使用
//	printf("%d\n", a);
//	return 0;
//}

////修饰局部变量
//void test()
//{
//    static int a = 1;                  //static ——将局部变量静态化，即延长其生命周期
//	a++;
//	printf("%d\n", a);                 //
//}                                      // 结果为:2，3，4，5，6
//                                       
//int main()
//{
//	int i = 0;
//	while (i < 5)
//	{
//		test();
//		i++;
//	}
//	return 0;
//}


//int main()
//{
//	// union——联合体/共用体
//	// struct——结构关键字
//	// typedef——类型定义——类型重定义
//	typedef unsigned int u_int;
//	u_int a = 0;
//
//	return 0;
//}


//            int
//int main()
//{
//	int a = 0;    //  int  定义的变量是有符号的
//	// signed int  缩写为  int 
//	unsigned int b = 0;        //  将变量定义为无符号的
//
//	return 0;
//}


////       register
//int main()
//{                                       
//	register int a = 10;      //建议将a定义为寄存器变量
//	                           
//	                       //    寄存器——>高速缓存——>内存——>硬盘
//	return 0;
//}


////   auto
//int main()
//{
//    int a = 0;      //局部变量——自动变量
//	return 0;
//}

//int main()
//{
//	int num1 = 0;
//	int num2 = 0;
//	int max = 0;
//	scanf("%d%d", &num1, &num2);
//                             //    (exp1?exp2:exp3)    当exp1判断为真时，输出exp2，为假时，输出exp3              三目操作符
//	max = (num1 > num2 ? num1 : num2);
//	printf("%d\n", max);
//
//	return 0;
//}

////  &&  ——逻辑与   ||  ——  逻辑或
//int main()
//{
//	//  假  ——  0
//	//  真  ——  非0
//	//  &&  ——  逻辑与       两者同时为真才为真
//	//  ||  ——  逻辑或       两者有一为真即为真  
//	int a = 0;
//	//int a = 3;
//	//int b = 5;
//	int b = 0;
//	int c = a || b;
//	//int c = a && b;
//	printf("c = %d\n", c);
//	return 0;
//}

////  （类型）
//int main()
//{
//	int a = 3.14;                    //  (类型)  强制定义字符
//	int b = (int)3.14;
//	return 0;
//}

////  前后置++    前后置--
//int main()
//{
//	    int a = 10;
//	    //int b = a++;                          //后置++，先使用，再++                  //  b = 10  ,  a = 11
//    	//int b = ++a;                          //前置++，先++，再使用                  //  b = 11  ,  a = 11
//		//int b = a--;                          //后置--，先使用，再--                  //  b = 10  ,  a = 9   
//		int b = --a;                            //前置--，先--，再使用                  //  b = 9   ， a = 9    
//		printf("\ta = %d\tb = %d\n", a, b);     // 
//
//	return 0;
//}

////  ~  取反           原码、反码、补码
//int main()
//{
//	int a = 0;                    //4个字节，32bit位
//	int b = ~a;                   //b是有符号的整形
//	                             //按（二进制）位取反
//	                             //原码、反码、补码
//	                                              //   第一位数字代表的是正负数   1代表的是负数   0代表的是正数
//
////                              正数——原码、反码、补码相同
////                               负数     原码                   ——>           反码                     ——>      补码
//                                    // 直接按照正负                       原码的符号位不变                         反码+1   
//                                    // 写出的二进制序列                     其他按位取反
//
//								 //负数在内存中存储的是二进制的补码
//	                             //111111111111111111111111111111111                  补码
//	                             //111111111111111111111111111111110                  反码：补码减一得到反码
//	                             //100000000000000000000000000000001                  原码：反码符号位不变，其他位取反得到原码
//	                             
//	printf("%d\n", b);           //使用的、打印的是这个数的原码
//
//	return 0;
//}

//sizeof
//int main()
//{
//	int a = 0;
//	int arr[] = { 1,2,3,4,55,6,7,8 };                         // sizeof ——计算存储空间大小，单位是字节
//	printf("%d\n", sizeof a );                                //4
//	printf("%d\n", sizeof(int));                              //4
//	printf("%d\n", sizeof arr);                               //32        sizeof——计算数组大小，单位是字节
//	printf("%d\n", sizeof arr / sizeof arr[0]);               //8
//
//	return 0;
//}

////取两者中较大者
//int Max(int x, int y)
//{
//	if (x > y)
//		return x;
//	else
//		return y;
//}
//int main()
//{
//	int num1 = 0;
//	int num2 = 0;
//	int max = 0;
//	scanf("%d%d", &num1, &num2);
//	max = Max(num1, num2);
//	printf("%d\n", max);
//	return 0;
//}

//int main()
//{
//	int num1 = 0;
//	int num2 = 0;
//	scanf("%d%d",&num1,&num2);
//	if (num1 > num2)
//		printf("%d\n", num1);
//	else
//		printf("%d\n", num2);
//
//	return 0;
//}

////除号、取模
//int main()
//{
//	int a = 5 / 2;
//	printf("%f\n", a);                //除法只取整数商
//	return 0;
//}

//int main()
//{
//	int a = 5 % 2;                     // %——取模       取除法产生的余数   
//	printf("%d\n", a);
//	return 0;
//}

////数组
//int main()
//{
//	//int a = 0;
//	//int b = 1;
//	//int c = 2;
//	//int d = 3;
//	int arr[10] = { 0,1,2,3,4,5,6,7,8,9 };     //定义一个存放10个整型数字的数组
//	//0-9
//	int i = 0;
//	while (i < 10)
//	{
//		printf("%d", arr[i]);
//		i++;
//	}
//	//printf("%d\n",arr[4]);                   //以下标的形式访问元素
//	//数组中的每一个元素都会有一个下标      作为它的地址
//
//	return 0;
//}

//
//循环语句
//int main()
//{
//	int line = 0;
//	printf("开始上课");
//
//	while (line < 20000)                        //while、if语句后无需加分号
//	{
//		printf("敲一行代码，%d\n", line);
//		line++;
//	}
//	if (line >= 20000)
//
//	printf("考上研");
//
//	return 0;
//}


////if语句
//int main()
//{
//	int input = 0;
//	   printf("加入字节跳动\n");
//	   printf("你是否好好学习？, (0/1)>:");
//	scanf("%d", &input);
//	if (input == 1)
//	   printf("欢迎加入\n");
//	else
//	   printf("回家种红薯\n");
//
//		return 0;
//}

////转义字符 
//int main()
//{
//	//printf("%d\n",strlen("qwerwr\tkjshkfj\thihdf\tdsf"));                //转义字符只算一个字符   即：\121 为一个字符
//	//printf("%c\n", '\5');
//	//printf("%c\n", '\x61');           //   \xdd  即十六进制的两个数字  注意： 只有两个数字，例：\x22
//	return 0;
//
//}

//int main()
//{
//	//printf("qewr\tdf\n");            //  \t  的作用
//	printf("qwe\\tdfgjsd\\34n\n");       //   //用来防止转义斜杠，即输出斜杆
//	return 0;
//}

//int main()
//{
//	printf("abc\n");              //转义字符    \+字母  即： \n ——换行  ， \t ——水平制表符（空白两格）
//	return 0;
//}


////字符串
//int main()
//{
//	char arr1[] = "abc";
//	char arr2[] = { 'a','b','c','\0'};
//	printf("%d\n",strlen(arr1));        //strlen  ——  string lenth  计算字符串长度
//	printf("%d\n",strlen(arr2));        //不加\0则为随机值
//	return 0;
//}

//int main()
//{
//	                                     //数据在计算机储存时用的是二进制
//	                                     //a-97   ，     A-65   
//	                                     //ASCⅡ编码
//	                                     //ASCⅡ码值
//	char arr1[] = "abc";                  //数组
//	                                      //"abc" —— 'a','b','c','\0' —— '\0'字符串结束的标志
//	                                      //"" —— 默认自带'\0'
//	                                      //'' —— 需要自行打上结束标志，如：'\0' , 0
//	char arr2[] = { 'a' ,'b' ,'c',0 };
//	printf("%s\n", arr1);                  //打印字符串用的是%s
//	printf("%s\n", arr2);
//
//	return 0;
//}


////字符串 ： 由双引号（Double Quote）引起来的一串字符称为字符串字面值
////字符串的结束标志是一个\0的转义字符。在计算字符串长度的时候\0是结束标志，不算作字符串内容
////字符串类型
//int main()
//{
//	//例：
//	"skdhjsdfh";
//	"123";
//	"";                    //空字符串
//	return 0;
//}


//4.  枚举常量
//枚举   ：一一列举
//性别：男、女
//三原色：红、黄、蓝

//枚举关键字  ——  enum

//enum Color
//{
//	RED,
//	YELLOW,
//	BLUE
//};
//int main()
//{
//	enum Color color = BLUE;
//	printf("%d\n", color);                      
//	// Color = 6;                  //枚举常量不可修改
//	return 0;
//}

////性别
//enum Sex
//{
//	MALE,
//	FEMALE,
//	SECRET
//};
////枚举常量：MALE、FEMALE、SECRET
//
//int main()
//{
//	//enum Sex s = FEMALE;
//	printf("%d\n", MALE);
//	printf("%d\n", FEMALE);
//	printf("%d\n", SECRET);                         //枚举常量不可修改
//	return 0;                                
//}

////3.  #define定义的标识符常量
//#define MAX 10
//int main()
//{
//	int arr[MAX] = { 0 };
//	printf("%d\n", MAX);
//
//	return 0;
//}

//// 2.  const修饰的常量  1.  字面常量
//int main()
//{
//	//const 常变量                                      字面常量即  3 ， 400  
//    //const 修饰的常变量
//	const int num = 4;
//	printf("%d\n", num);
//	num = 5;
//	printf("%d\n", num);
//
//	return 0;
//}

////使用标准C语言规则
//int main()
//{
//	int num1 = 0;
//	int num2 = 0;
//	int sum = 0;
//	scanf("%d%d", &num1, &num2);
//	sum = num1 + num2;
//	printf("sum = %d\n", sum);
//
//	return 0;
//}

////计算两个数的和
//int main()
//{
//	int num1 = 0;
//	int num2 = 0;
//	int sum = 0;
//
//	//输入数据——使用输入数据函数scanf
//	scanf("%d%d", &num1, &num2);                        //取地址符号&                    
//	//C语言语法规定，变量要定义在代码块的最前面（C++可以随用随定义
//	sum = num1 + num2;
//	printf("sum = %d\n", sum);
//
//	return 0;
//}

////作用域
//int main()
//{
//	//为声明的标识符
//	//extern：声明外部符号的
//	extern int num;
//	printf("%d\n", num);
//	return 0;
//}


////作用域、生命周期
//void test()
//{
//	int a = 1;
//	a++;
//	printf("%d\n", a);                 //局部变量出作用域即销毁
//}                                      //每次都是将 1 赋值給 a 
//									   //再++，即 a = 2      如此重复5次，打印5个2
//int main()
//{
//	int i = 0;
//	while (i < 5)
//	{
//		test();
//		i++;
//	}
//	return 0;
//}


//全局变量的使用
//    int a = 20;
//	int main()                               //作用域：名字的可用性的作用范围
//{
//		printf("%d\n", a);                   //全局变量的作用域是整个工程（一个源文件定义的全局变量，所有源文件都可以使用）
//                                       
//		return 0;                             //全局变量则不用在同一个代码块内
//}

//局部变量的使用
//int main()
//{
//	{
//		int a = 20;
//	}
//	printf("%d\n", a);                      //局部变量的作用域是变量所在的局部范围
//
//	return 0;                                 //局部变量需在同一个代码块内
//}

//	//变量
////     int num2 = 20;                                                               //定义在代码块（{}）之外的变量称为全局变量
//int a = 100;   //全局变量
//int main()
//{
//	//		 int num1 = 10;                                                           //定义在代码块（{}）内部的变量称为局部变量
//	int a = 20;  //局部变量
//	printf("%d\n", a);
//	//局部变量与全局变量的名字建议不要相同，容易误会，产生bug
//	//当局部变量与全局变量名字相同时，局部变量优先
//	return 0;
//}


////内存空间
//int main()
//{
//	//年龄
//		short int age = 20;                                                      //向内存申请两个字节 = 16个bit位的空间 ， 用来存放20
//		float weight = 99.6f;                                     //向内存申请四个字节的空间 ， 用来存放99.6 ，f是指定小数为单精度浮点型
//		printf("%d\n", age);
//		printf("%f\n", weight);
//return 0;
//}


////数据类型占据内存大小
//int main()
//{
//		                                                                              //size of (...)  ...的空间大小
//		                                           // 一个字节 = 八个比特    一个比特即一个 0 或 1
//		printf("%d\n", sizeof(char));                                                   //一个字节   使用了一个字节大小的内存空间                            
//		printf("%d\n", sizeof(short));                                                  //两个字节
//		printf("%d\n", sizeof(int));                                                    //四个字节
//		printf("%d\n", sizeof(long));                                                   //四个字节
//		printf("%d\n", sizeof(long long));                                              //八个字节
//		printf("%d\n", sizeof(float));                                                  //四个字节
//		printf("%d\n", sizeof(double));                                                 //八个字节
//return 0;
//}


////打印数据类型
//int main()
//{
//	char ch = 'A';                                                                   //内存
//	printf(" %c\n" , ch );                                                        //%c - 打印字符格式的数据
//return 0;
//}
//	//                                     char , int , long , long long ， float 等 表示向内存申请不同大小的空间  用以存储不同的数据类型
//	//                                                                                 short int —— 短整型 
//	//                                                                                    long  —— 长整型



////打印数据类型
//int main()
//{
//	int age = 20;
//	printf("%d\n", age);                                                               //%d —— 打印整型十进制的数据
//	long num = 100;
//	printf("%d\n", num);
//	float f = 5.0;
//	printf("%f\n", f);
//	double d = 3.14;
//	printf("%lf\n", d);
//return 0;
//}

																					//%c —— 打印字符
																					//%d —— 打印整型
																					//%s —— 打印字符串
																					//%f —— 打印浮点数 - 打印小数
																					//%lf —— 打印双精度浮点数
																					//%p —— 以地址的形式打印
																					//%x —— 打印十六进制

//   // Hello world
//int main()                                                                      //主函数-程序的入口-main函数的入口有且仅有一个
//																				//int是整型的意思    main前面的int表示main函数调用返回一个整型值
//{
//	//这里完成任务 
//	//在屏幕上输出hello world
//	printf(" hello world\n ");                                                    //函数 print - funtion - 打印函数
//	return 0;                                                                     //与int函数相呼应，返回一个整型值
//}
