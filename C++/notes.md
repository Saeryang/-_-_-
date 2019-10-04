# C++ 수업
---
#목차  
[(10월 4일)](#2019-10-04)  
[--CASE문](#CASE문)  
[--배열](#배열)  
[--구조](#구조)  
[--포인터](#포인터)  
[--연결리스트](#연결리스트)  
## 2019-10-04
### CASE문
```
#include "stdafx.h"
#include <iostream>
using namespace std;
 
int main()
{
	
	while(1)
	{
		cout << "------메뉴------"<< endl;
		cout << "1. 학생 성적 추가"<< endl;
		cout << "2. 전체 성적 보기"<< endl;
		cout << "Q. 프로그램 종료"<< endl;
		cout << "-----------------"<< endl;
		cout << "원하는 작업의 번호를 입력하세요 : "<< endl;
 
	    char select;
		cin >> select;
 
		switch(select)
		{
		case'1':
			cout << "학생 성적 추가가 선택 되었습니다."<< endl ;
			break;
		case'2':
			cout <<"전체 성적 보기가 선택 되었습니다."<< endl;
			break;
		case'Q':
		case'q':
			cout << "프로그램을 종료합니다."<< endl;
			return 0;
		default:
			cout<< "올바른 값을 입력해 주세요."<< endl;
			break;
		}
	}
	return 0;
}
 
```
---
* 문제점 검토 필요
```
#include "stdafx.h"
#include <iostream>

using namespace std;
 
 
int main()
{
	while(1)
	{
		// print menu
		cout << "\n-----메뉴-----\n" <<endl;
		cout << "1.  학생 성적 추가" <<endl;
		cout << "2.  학생 성적 보기" <<endl;
		cout << "Q.  프로그램  종료" <<endl;
		cout << "------------------" <<endl;
		cout << "번호를  입력하시오" <<endl;
 
		char select;
		cin >> select;
 
		switch(select) 
			{
			case '1':
				cout << " 성적 추가 선택";
				break;
			case '2':
				cout << " 성적 보기 선택";
				break;
			
			case 'q':
			case 'Q':
				cout << "프로그램 종료";
				return;
		
			default:
				cout << "올바른 값을 입력하시오";
				break;
			}
	}
	return 0;
}
```
---
### 배열
```
#include "stdafx.h"
#include <iostream>

using namespace std;

int main()
{
	char example[] = "scientia est potentia"; //null까지 포함됨
	char example1[100];
	int i;

	cout <<example << endl;
	for(i=0;i<sizeof(example)-1;i++)
	{
		example1[i] = example[(sizeof(example)-2)-i];
	}
	example1[i] = NULL; //문자열출력시 꼭 NULL을 삽입해주도록 하자

	cout << example1 << endl;

	return 0;
}
```
---
### 구조
* 구조체(struct)기본
```
#include "stdafx.h"
#include <iostream>

using namespace std;

int main()
{
	struct StudentInfo // 구조체 생성
	{
		char blood;
		int id;
		float grade;
	};

	StudentInfo si1 = {'A',20141331,3};
	cout << si1.blood << endl;
}
```
---
### 포인터
* 포인터 기본 정리
```
#include "stdafx.h"
#include <iostream>

using namespace std;

int main()
{
	int a = 123;
	int* p;
	p = &a;

	cout << "a = " << a << endl; // a값
	cout << "&a = " << &a << endl; // a의 주소값
	cout << "p = " << p << endl; // p값
	cout << "*p = " << *p << endl; // p의 주소가 가리키는 값
	cout << "&p = " << &p << endl; // p도 변수이므로 주소가 있음

	cout << "-----" << endl;

	*p = 789; // p가 가리키는 값에 789 대입,
	
	cout << "a = " << a << endl; // 대입후 a값
	cout << "&a = " << &a << endl; // a의 주소값
	cout << "p = " << p << endl; // p값
	cout << "*p = " << *p << endl; // p의 주소가 가리키는 값
	cout << "&p = " << &p << endl; // p도 변수이므로 주소가 있음
}
```
---
### 연결리스트
* 기본.
```
#include "stdafx.h"
#include <iostream>

using namespace std;

struct Dizzy
{
	int id; // 고유값
	Dizzy* p; // 포인터
};

int main()
{
	Dizzy a,b,c;
	a.id =1; b.id = 4; c.id = 7; // Doyagao
	a.p = &b;
	b.p = &c;
	c.p = 0; // 0번지에 뭐가 있다?X , 0 = 주소를 할당받지 않음 = 끝이다.
	cout << "a값" << a.id << endl; // a값
	cout << "b값" << b.id << endl; // a값
	cout << "c값" << c.id << endl; // a값
	cout << "a.p->id : " << a.p->id << endl;
	cout << "a.p->p->id : " << a.p->p->id << endl;

}
```
---
* 심화 - for 문으로 다수의 연결 리스트
```
#include "stdafx.h"
#include <iostream>

using namespace std;

struct Dizzy
{
	int id; // 고유값
	Dizzy* p; // 포인터
};

int main()
{
	Dizzy data[10];
	for(int i=0;i<=9;i++) // linked list로 연결됨
	{
		data[i].id = i;
		data[i].p = &data[i+1]; 
		
	}
	data[9].p = 0; // 주소할당 끝
	
	Dizzy* p = &data[0];
	while(p != 0)
	{
		cout << p->id <<endl;
		p = p->p;
	}
}
```
---
* 삭제
```
#include "stdafx.h"
#include <iostream>

using namespace std;

struct Dizzy
{
	int id; // 고유값
	Dizzy* p; // 포인터
};

int main()
{
	Dizzy data[10];
	for(int i=0;i<=9;i++) // linked list로 연결됨
	{
		data[i].id = i;
		data[i].p = &data[i+1]; 
		
	}
	data[9].p = 0; // 주소할당 끝
	
	Dizzy* p = &data[0];
	
	//id가 4번인걸 삭제하고싶다?
	cout << "<--4번 삭제-->" << endl;

	while(p != 0)
	{
		if(p->id == 3)
		{
			p->p = (p->p)->p;
			break;
		}
		cout << p->id <<endl;
		p = p->p;
	}

	while(p != 0)
	{
		cout << p->id <<endl;
		p = p->p;
	}
}
```
---
* 둘 다 출력
```
#include "stdafx.h"
#include <iostream>

using namespace std;

struct Dizzy
{
	int id; // 고유값
	Dizzy* p; // 포인터
};

int main()
{
	Dizzy data[10];
	for(int i=0;i<=9;i++) // linked list로 연결됨
	{
		data[i].id = i; data[i].p = &data[i+1]; 
		
	}
	data[9].p = 0; // 주소할당 끝
	
	Dizzy* p = &data[0];
		while(p != 0)
	{
		cout << p->id <<endl;
		p = p->p;
	}
		p = &data[0];

//id가 4번인걸 삭제하고싶다?
	cout << "<--4번 삭제-->" << endl;

	while(p != 0)
	{
		if(p->id == 3)
		{
			p->p = (p->p)->p;
			break;
		}
		p = p->p;
	}
	p = &data[0];
	while(p != 0)
	{
		cout << p->id <<endl;
		p = p->p;
	}
}
```
