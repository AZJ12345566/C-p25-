# C-p25-
C语言学习笔记 p25初识结构体
#include<stdio.h>
//描述一个学生-需要一些数据
struct Stu//struct Stu-结构体类型    struct结构体关键字    Stu-结构体标签
{
    //成员变量
    char nasme[20];
    short age;
    char tele[12];
    char sex[5];
}s1,s2,s3；//这个是变量列表，是三个全局的结构体变量，一般不推荐使用全局变量

int main()
{
    struct Stu s;//局部变量
    return 0;
}

typedef struct Stu
{
    //成员变量
    char nasme[20];
    short age;
    char tele[12];
    char sex[5];
}Stu；//这个结构体的意思是将上面的代码直接命名为Stu，这个Stu可以直接引用
//12行和27行的代码是不一样的，一个是变量一个是类型


int main()
{
    Stu s1={"张三“，20，”15249287076“,"男"}；//局部变量
    struct Stu s2={"旺财",30,"15596668862","保密"};//以上赋值的过程就是初始化
    return 0;
}


struct S
{
    int a;
    char c;
    char arr[20];
    double d;
};

struct T
{
    char ch[10];
    struct S s;
    char* pc;
};

int main()
{
    struct T t={"hehe",{100,'w',"hello world,3.14},NULL};
    printf("%s\n",t.ch);//hehe
    printf("%s\n",t.s.arr);//hello world
    printf("%lf\n",t.s.d);//3.14
    printf("%s\n",t.pc);//NULL
}


void Ptint1(Stu tmp)
{
    printf("name:%s\n",tmp.name);
    printf("age:%d\n",tmp.age);
    printf("tele:%s\n",tmp.tele);
    printf("sex:%s\n",tmp.sex);
}
void Print2(Stu* ps)
{
    printf("name:%s\n",ps->name);
    printf("age:%s\n",ps->age);
    printf("tele:%s\n",ps->tele);
    printf("sex:%s\n",ps->sex);
}
int main()
{
    Stu s={"李四",40,"15578886777","男"};
    //打印结构体的数据
    //这两种打印还是传址的方式更好
    Print1(s);
    Print2(&s);
    return 0;
}


int Add(int x,int y)
{
    int z=0;
    z=x+y;
    return z;
}
int main()
{
    int a=10;
    int b=20;
    int ret=0;
    ret=Add(a,b);
    return 0;
}

//栈：先进后出，后进先出，放入一个元素叫压栈，拿出一个元素叫出栈
