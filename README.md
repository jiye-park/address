#include<iostream>

using namespace std;
struct arr
{
	string name;
	string number;
};


int main()
{
	arr A[100];
	string b;
	string c;
	int a;
	int d;
	int e;
	int k = 0;
	int j = 0;
	string x;
	string y;
	while (j < 100)
	{
		j++;
		cout << "1.추가하기  " << "2.조회하기  " <<"3.수정하기  "<< "4.삭제하기  "<<"5.검색하기  "<< "6.나가기\n";
		cin >> a;
		if (a == 1)
		{
			cout << "이름과 전화번호를 차례로 입력해 주세요.\n";
			cin >> b;
			cin >> c;
			cout << "주소록에 추가 되었습니다." << endl;
			A[k] = arr{ b,c };
			k = k + 1;
		}
		else if (a == 2)
		{
			for (int i = 0; i < k; i++)
			{
				cout << A[i].name <<" "<< A[i].number << endl;
			}
		}
		else if (a == 3)
		{
			cout << "배열 번호를 입력 하십시오(0번부터 시작)" << endl;
			cin >> d;
			cout << A[d].name << " " << A[d].number << endl;
			cout << "수정할 이름과 전화번호를 입력 하십시오." << endl;
			cin >> x;
			cin >> y;
			A[d] = arr{ x, y };
			
			cout << "수정 되었습니다." << endl;
		}
		else if (a == 4)
		{
			cout << "배열 번호를 입력 하십시오(0번부터 시작)" << endl;
			cin >> d;
			cout << A[d].name << " " << A[d].number <<" 을 삭제 하시겠습니까?"<< endl;
			cout << "확인->1번, 취소->2번" << endl;
				cin >> e;
				if (e == 1)
				{
					for (d; d < k; d++)
					{
						A[d] = A[d+1];
					
					}
			}
				else if (e == 2)
				{
					continue;
				}
				else
				{
					cout << "다시 입력해 주십시오" << endl;
				}
		}
		else if(a == 5)
		{
			cout << "검색할 이름을 입력하십시오." << endl;
			cin >> x;
			bool Name = 0;
			for (int d=0; d < k; d++)
			{
				if (x == A[d].name)
				{
					cout << "검색하신 번호는 " << A[d].number << " 입니다." << endl;
					Name = true;
				}
			}
			if (Name == false)
			{
				cout << "검색된 내용이 없습니다." << endl;
			}
		}
		else if (a == 6)
		{
			break;
		}
		else
		{
			cout << "1번과 2번중에 선택해 주십시오." << endl;
		}
	}
	return 0;
}
