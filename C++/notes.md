# C++ 수업
## 2019-10-04
### CASE문
* 확인 요망
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
### 
