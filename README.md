###进制转换法

```cpp
//进制转化
#include<bits/stdc++.h>
using namespace std;
int turn(char c)
{
	if(c=='0')	return 0;
	if(c=='1')	return 1;
	if(c=='2')	return 2;
	if(c=='3')	return 3;
	if(c=='4')	return 4;
	if(c=='5')	return 5;
	if(c=='6')	return 6;
	if(c=='7')	return 7;
	if(c=='8')	return 8;
	if(c=='9')	return 9;
	if(c=='A')	return 10;
	if(c=='B')	return 11;
	if(c=='C')	return 12;
	if(c=='D')	return 13;
	if(c=='E')	return 14;
	if(c=='F')	return 15;
}
void dc(int x,int m)
{
	stack<char> s;
	int cnt=0;
	while(x!=0)
	{
		cnt++;
		if(x%m==10)			s.push('A');
		else if(x%m==11)	s.push('B');
		else if(x%m==12)	s.push('C');
		else if(x%m==13)	s.push('D');
		else if(x%m==14)	s.push('E');
		else if(x%m==15)	s.push('F');
		else				s.push(x%m+'0');
		x/=m;
	}
	for(int i=1;i<=cnt;i++)
	{
		cout<<s.top();
		s.pop();
	}
}
int main ()
{
	int n,m;
	cin>>n;
	string s;
	cin>>s;
	cin>>m;
	int len=s.size();
	int ans=0;
	if(m==10)
	{
		for(int i=0;i<len;i++)
		{
			int num=turn(s[len-1-i]);
			ans+=num*pow(n,i);
		}
		cout<<ans<<endl;
	}
	else
	{
		for(int i=0;i<len;i++)
		{
			int num=turn(s[len-1-i]);
			ans+=num*pow(n,i);
		}
		dc(ans,m);
	} 
	return 0;
}
//This program was written by Deng Zhongxuan

```
