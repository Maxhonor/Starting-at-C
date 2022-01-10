# Starting-at-C
/*#include<stdio.h>
//加法运算
int main()
{
	int a, b, c;
	scanf("%d %d", &a, &b);
	c = a + b;
	if(b>0)
	{
		printf("%d+%d=%d\n", a,b,c);
	}
	else
	{
		printf("%d+(%d)=%d\n", a, b, c);
	}
	return 0;
}*/
/*#include<stdio.h>
//鸡兔同笼问题
int main()
{
	int m, n, x, y;
	scanf("%d %d", &m, &n);
	x = 2 * m - n / 2;
	y = n / 2 - m;
	printf("chicken=%d,", x);
	printf("rabbits=%d", y);
	return 0;
}*/
//输入圆半径输出园的周长和面积
/*#include<stdio.h>
int main()
{
	float p = 3.1415926;
	float c, s;
	int r;
	scanf("%d", &r);
    c = 2 * r*p;
	s = p * r*r;
	printf("%.2f,%.2f", c, s);
	return 0;
}*/
/*#include<stdio.h>
//求三个整数的最大数
int main()
{
	int a, b, c,max;
	scanf("%d,%d,%d", &a, &b, &c);
	max = a;//假设其最大值为a
	if (max < b)
		max = b;
	if (max < c)
		max = c;
	printf("max=%d", max);
	return 0;
}*/
/*#include<stdio.h>
//请根据以下情况根据x的值求y的值：
//（1）当x < 1时，y = x
//（2）当1≤x < 10时，y = 2x - 1
//（3）当x≥10时，y = 3x - 11
int main()
{
	float x, y;
	scanf("%f", &x);
	if (x < 1)
		y = x;
	else if (x >= 1 && x < 10)
		y = 2 * x - 1;
	else
		y = 3 * x - 11;
	printf("x=%.3f,y=%.3f", x, y);
	return 0;
}*/
/*#include<stdio.h>
//给出一百分制成绩，输出成绩等级
int main()
{
	int a;
	scanf("%d", &a);
	if (a >= 90)
		printf("grade=A");
	else if (a >= 80 && a <= 89)
		printf("grade=B");
	else if (a >= 70 && a <= 79)
		printf("grade=C");
	else if (a >= 60 && a <= 69)
		printf("grade=D");
	else
		printf("grade=E");
	return 0;
}*/
/*#include<stdio.h>
#include<math.h>
//正序和逆序输出一个正整数的各个位
//从键盘上输入一个不多于5位（包括5位）的正整数，要求：
//（1）求出它是几位数；
//（2）分别输出每一位数字（数据最小宽度为2）；
//（3）按逆序输出各位数字（数据最小宽度为2）。
int main()
{
	int n,num,gw,sw,bw,qw,ww;
	scanf("%d", &n);
	num = log10(n) + 1;//运用数学公式得到几位数
	gw = n % 10;//取模运算得到个位数以此类推
	sw = n / 10 % 10;//十位数
	bw = n / 100 % 10;//百位数
	qw = n / 1000 % 10;//千位数
	ww = n / 10000 % 10;//万位数
	if(num==1)
	printf("num=1，natural order:%2d,reverse order:%2d", n,n);
	if (num == 2)
		printf("num=2，natural order:%2d %2d,reverse order:%2d %2d", sw, gw,gw,sw);
	if (num == 3)
		printf("num=3，natural order:%2d %2d %2d,reverse order:%2d %2d %2d", bw, sw, gw, gw, sw, bw);
	if (num == 4)
		printf("num=4，natural order:%2d %2d %2d %2d,reverse order:%2d %2d %2d %2d", qw, bw, sw, gw, gw, sw, bw, qw);
	if(num==5)
		printf("num=5，natural order:%2d %2d %2d %2d %2d,reverse order:%2d %2d %2d %2d %2d",ww, qw, bw, sw, gw, gw, sw, bw, qw,ww);
	return 0;
}*/
/*#include<stdio.h>
//根据利润计算奖金(switch)
//企业发放的奖金根据利润提成。
//（1）利润I低于或等于10万元时，奖金可提成10% ；
//（2）利润高于10万元，低于20万元（100000 < I≤200000）时，其中10万元按10%提成，高于10万元的部分，可提成7.5% ；
//（3）200000 < I≤400000时，其中20万元仍按上述办法提成（下同），高于20万元的部分按5%提成；
//（4）400000 < I≤600000时，高于40万元的部分按3%提成；
//（5）600000〈I≤1000000时，高于60万的部分按1.5%提成；
//（6）I>1000000时，超过100万元的部分按1%提成。
//从键盘输入当月利润I（单位为万元），求应发放奖金总数（保留4位小数）。
//数据类型选择double。
int main()
{
	double p=0;
	double b;
	scanf("%lf", &p);
	double b1 = 10 * 0.1;
	double b2 = b1 + 10 * 0.075;
	double b3 = b2 + 20 * 0.05;
	double b4 = b3 + 20 * 0.03;
	double b5 = b4 + 40 * 0.015;
	int s;//作为switch语句里的整形变量
	s = (int)p / 10;//找到这些的最大公约数作为switch语句里的整形常量
	//强制类型装换从double->int 
	if (s > 10)
		s = 10;
	switch(s)
	{ 
		case 0:
			b = p * 0.1;
			break;
		case 1:
			b = b1 + (p - 10)*0.075;
			break;
		case 2:
		case 3:
			b = b2 + (p - 20)*0.05;
			break;
		case 4:
		case 5:
			b = b3 + (p - 40)*0.03;
			break;
		case 6:
		case 7:
		case 8:
		case 9:
			b = b4 + (p - 60)*0.015;
			break;
		case 10:
			b = b5 + (p - 100)*0.01;
			
	}

	//if (p < 10)//s为0
	//	b = p * 0.1;
	//else if (p < 20)//s为1
	//	b = b1 + (p - 10)*0.075;
	//else if (p < 40)//s为2、3
	//	b = b2 + (p - 20)*0.05;
	//else if (p < 60)//s为4、5
	//	b = b3 + (p - 40)*0.03;
	//else if (p < 100)//s为6、7、8、9
	//	b = b4 + (p - 60)*0.015;
	//else//s为10、11、12、13...
	//	b = b5 + (p - 100)*0.01;

	printf("profit=%.4lf,bonus=%.4lf", p, b);
	return 0;
}*/

/*#include<stdio.h>
//四个数中从小到大顺序进行排序
int main()
{
	int a, b, c, d,t;
	scanf("%d%d%d%d", &a, &b, &c, &d);
	//先找到最小值俩俩进行比较或找最大值
	if (a > b) { t = a; a = b; b = t; }
	if (a > c) { t = a; a = c; c = t; }
	if (a > d) { t = a; a = d; d = t; }
	//在b,c,d中找到最小值b或大
	if (b > c) { t = b; b = c; c = t; }
	if (b > d) { t = b; b = d; d = t; }
	//在c,d中找出最小值c或大
	if (c > d) { t = c; c = d; d = t; }
	printf("%d %d %d %d", a, b, c, d);
	return 0;
}*/
/*#include<stdio.h>
//用switch语句处理菜单命令：+ - * /运算
int main()
{
	int a, b, d;
	char c;
	scanf("%d,%d,%c", &a, &b, &c);
	switch (c)//字符型变量
	{
		//字符型常量类比整形
	case'+':
		d = a + b;
		printf("%d+%d=%d", a, b, d);
		break;
	case'-':
		d = a - b;
		printf("%d-%d=%d", a, b, d);
		break;
	case'*':
		d = a * b;
		printf("%d*%d=%d", a, b, d);
		break;
	case'/':
		d = a / b;
		printf("%d/%d=%d", a, b, d);
		break;
	}
	return 0;
}*/

#include<stdio.h>
//从键盘上输入一个年份，判断是否为闰年，输出相应结果。
//闰年的条件：1.能够被4整除且不能够被100整除的年份；2.能够被400整除的也是闰年。
//两个条件满足其一即可，若都不满足即非闰年
int main()
{
//(a % 4 == 0 && a % 100 != 0) || a % 400 == 0 ?//判断语句 (printf("%d is a leap year.", a)) : (printf("%d is not a leap year.", a));
	int a;
	scanf("%d", &a);
	if (a % 4 == 0 && a % 100 != 0)
		printf("%d is a leap year.", a);
	else if (a % 400 == 0)
		printf("%d is a leap year.", a);
	else
		printf("%d is not a leap year.", a);
	return 0;
}

                                      






