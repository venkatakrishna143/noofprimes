# noofprimes

#include<bits/stdc++.h>
#define N 1000000
using namespace std;
int main()
{
    bool isprime[N+5];
    isprime[0]=isprime[1]=0;
    for(int i=2;i<=1000000;i++)isprime[i]=1;
    int n;
    cin>>n;
    for(int i=2;i*i<=n;i++)
    {
        if(isprime[i])
        {
            for(int j=i*i;j<=n;j+=i)
                isprime[j]=0;
        }
    }
    int cnt=0;
    for(int i=0;i<=n;i++)if(isprime[i])cnt++;
    cout<<cnt<<"\n";
    return 0;
}
