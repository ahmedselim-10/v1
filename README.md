#include<iostream>
using namespace std;
int main() {
	int n, m, t;
    cout<<"Enter number of row. and col. : ";
	cin >> n >> m;
	int di[] = { 0,1,0,-1 };
	int dj[] = { 1,0,-1,0 };
	int drx = 0, dry = 0;
	cout<<"How many motions do you want ?"<<endl;
	cin>> t;
	for (int i = 0; i < t; i++)
	{
		int c, x;
		cout<<"Enter your motion and how many do you want to use it :"<<endl<<"1-Up"<<endl<<"2-Right"<<endl<<"3-Down"<<endl<<"4-Left"<<endl;
		cin >> c >> x;
		c -= 1;
		for (int i = 0; i < x; i++)
		{
			if ((drx + 1 == n && (c == 0 || c == 1)) || (dry + 1 == m && (c == 0 || c == 1)))
				c += 2;
			else if ((drx == 0 && (c == 2 || c == 3)) || (dry == 0 && (c == 2 || c == 3)))
				c -= 2;
			drx += di[c];
			dry += dj[c];
			if(i+1==x)
			cout << drx << " " << dry << endl;

		}

	}
	return 0;
}

