    C++常用库函数

    1、常用数学函数
    头文件 #include <math> 或者 #include <math.h>

    函数原型	功能	返回值
    int abs(int x)	求整数x的绝对值	绝对值
    double acos(double x)	计算arcos(x)的值	计算结果
    double asin(double x)	计算arsin(x)的值	计算结果
    double atan(double x)	计算arctan(x)的值	计算结果
    double cos(double x)	计算cos(x)的值	计算结果
    double cosh(double x)	计算x的双曲余弦cosh(x)的值	计算结果
    double exp(double x)	求的值	计算结果
    double fabs(double x)	求实数x的绝对值	绝对值
    double fmod(double x)	求x/y的余数	余数的双精度数
    long labs(long x)	求长整型数的绝对值	绝对值
    double log(double x)	计算In(x)的值	计算结果
    double log10(double x)	计算的值	计算结果
    double modf(double x, double *y)	取x的整数部分送到y所指向的单元格中	x的小数部分
    double pow(double x, double y)	  求x的y次幂的值	计算结果
    double sin(double x)	计算sin(x)的值	计算结果
    double sqrt(double x)	求的值	计算结果
    double tan(double x)	计算tan(x)的值	计算结果
    fcvt	将浮点型数转化为字符串	 


    2、常用字符串处理函数
    头文件 #include <string> 或者 #include <string.h>

    函数原型	功能	返回值
    void *memcpy(void *p1, const void *p2 size_t n)	存储器拷贝，将p2所指向的共n个字节拷贝到p1所指向的存储区中	目的存储区的起始地址
    （实现任意数据类型之间的拷贝）
    void *memset(void *p int v, size_t n)	将v的值作为p所指向的区域的值，n是p所指向区域的大小	该区域的起始地址
    char *strcpy(char *p1, const char *p2)	将p2所指向的字符串拷贝到
    p1所指向的存储区中	目的存储区的起始地址
    char *strcat(char *p1, const
    char *p2)	将p2所指向的字符串连接到
    p1所指向的字符串后面	目的存储区的起始地址
    int strcmp(const char *p1, const char *p2)	比较p1,p2所指向的两个
    字符串的大小	两个字符串相同，返回0；若p1所指向的字符串小于p2所指的字符串，返回负值；否则，返回正值
    int strlen(const char *p)	求p所指向的字符串的长度	字符串所包含的字符个数
    （不包括字符串结束标志’\n’）
    char *strncpy(char *p1, const char *p2, size_t n)	将p2所指向的字符串（至多n个字符）拷贝到p1所指向的存储区中	目的存储区的起始地址
    (与strcpy()类似)
    char *strncat(char *p1, const char *p2, size_t n)	将p2所指向的字符串（至多n个字符）连接到p1所指向的字符串的后面	目的存储区的起始地址
    (与strcpy()类似)
    char *strncmp(const char *p1, const char *p2, size_t n)	比较p1,p2所指向的两个字符串的大小，至多比较n个字符	两个字符串相同，返回0；若p1所指向的字符串小于p2所指的字符串，返回负值；否则，返回正值
    (与strcpy()类似)
    char *strstr(const char *p1, const char *p2)	判断p2所指向的字符串是否是p1所指向的字符串的子串	若是子串，返回开始位置的地址；否则返回0。




    3、其他常用函数
    头文件#include <stdlib> 或者 #include <stdlib.h>
    函数原型	功能	返回值	说明
    void abort(void)	终止程序执行	 	不能结束工作
    void exit(int)	终止程序执行	 	做结束工作
    double atof(const char *s)	将s所指向的字符串转换成实数	实数值	 
    int atoi(const char *s)	将s所指向的字符串转换成整数	整数值	 
    long atol(const char *s)	将s所指的字符串转换成长整数	长整数值	 
    int rand(void)	产生一个随机整数	随机整数	 
    void srand(unsigned int)	初始化随机数产生器	 	 
    int system(const char *s)	将s所指向的字符串作为一个可执行文件，并加以执行	 	 
    max(a, b)	求两个数中的大数	大数	参数为任意类型
    min(a,b)	求两个数中的小数	小数	参数为任意类型





    4、实现键盘和文件输入/输出的成员函数
    头文件#include <iostream> 或者 #include <iostream.h>
    函数原型	功能	返回值
    cin >> v	输入值送给变量	 
    cout << exp	输出表达式exp的值	 
    istream & istream::get(char &c)	输入字符送给变量c	 
    istream & istream::get(char *, int , char = ‘\n’)	输入一行字符串	 
    istream & istream::getline(char *, int , char = ‘\n’)	输入一行字符串	 
    void ifstream::open(const char*,int=ios::in,
    int = filebuf::openprot )	打开输入文件	 
    void ofstream::open(const char*,int=ios::out,
    int = filebuf::openprot)	打开输出文件	 
    void fsream::open(const char*,int ,
    int = filebuf::openprot)	打开输入/输出文件	 
    ifstream::ifstream(const char*,int = ios::in,
    int = filebuf::openprot)	构造函数打开输入文件	 
    ofstream::ofstream(const char*,int=ios::out,
    int = filebuf::openprot)	构造函数打开输出函数	 
    fstream::fstream(const char*, int,
    int = filebuf::openprot)	构造函数打开输入/输出文件	 
    void istream::close()	关闭输入文件	 
    void ofsream::close()	关闭输出文件	 
    void fsream::close()	关闭输入/输出文件	 
    istream & istream::read(char*, int)	从文件中读取数据	 
    ostream & istream::write(const char*,int)	将数据写入文件中	 
    int ios::eof()	判断是否到达打开文件的尾部	1为到达2为没有
    istream & istream::seekg(streampos)	移动输入文件的指针	 
    istream & istream::seekg(streamoff,ios::seek_dir)	移动输入文件的指针	 
    streampos istream::tellg()	取输入文件的指针	 
    ostream & ostream::seekp(streampos)	移动输出文件的指针	 
    ostream & ostream::seekp(streamoff,ios::seek_dir)	移动输出文件的指针	 
    streampos ostream::tellp()	取输出文件的指针	 

    C++的头文件！ 
    #include <ctype.h>//字符处理 


    #include <errno.h>//定义错误码 


    #include <float.h>//浮点数处理 


    #include <fstream.h>//文件输入／输出 


    #include <iomanip.h>//参数化输入／输出 


    #include <iostream.h> //数据流输入／输出 


    #include <limits.h> //定义各种数据类型最值常量 


    #include <locale.h> //定义本地化函数 


    #include <math.h> //定义数学函数 


    #include <stdio.h> //定义输入／输出函数 


    #include <stdlib.h> //定义杂项函数及内存分配函数 


    #include <string.h> //字符串处理 


    #include <strstrea.h> //基于数组的输入／输出 


    #include <time.h> //定义关于时间的函数 


    #include <wchar.h> //宽字符处理及输入／输出 


    #include <wctype.h> //宽字符分类 




    标准 C++ （同上的不再注释） 


    #include <algorithm> //STL 通用算法 


    #include <bitset> //STL 位集容器 


    #include <cctype> 


    #include <cerrno> 


    #include <clocale> 


    #include <cmath> 


    #include <complex> //复数类 


    #include <cstdio> 


    #include <cstdlib> 


    #include <cstring> 


    #include <ctime> 


    #include <deque> //STL 双端队列容器 


    #include <exception> //异常处理类 


    #include <fstream> 
    #include <functional> //STL 定义运算函数（代替运算符） 


    #include <limits> 


    #include <list> //STL 线性列表容器 


    #include <map> //STL 映射容器 


    #include <iomanip> 


    #include <ios> //基本输入／输出支持 


    #include <iosfwd> //输入／输出系统使用的前置声明 


    #include <iostream> 


    #include <istream> //基本输入流 


    #include <ostream> //基本输出流 


    #include <queue> //STL 队列容器 


    #include <set> //STL 集合容器 


    #include <sstream> //基于字符串的流 


    #include <stack> //STL 堆栈容器 


    #include <stdexcept> //标准异常类 


    #include <streambuf> //底层输入／输出支持 


    #include <string> //字符串类 


    #include <utility> //STL 通用模板类 


    #include <vector> //STL 动态数组容器 


    #include <cwchar> 


    #include <cwctype> 


    using namespace std; 
