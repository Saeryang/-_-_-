# C++ 수업
## 2019-10-04
###
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
