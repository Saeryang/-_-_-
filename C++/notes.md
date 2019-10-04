# C++ 수업
## 2019-10-04
### CASE문[공백]
```
blank
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

}
```
### 
