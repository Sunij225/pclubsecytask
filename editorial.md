# sort-usinghcf
## Tutorial
In this question, you have to go at each prime indices and check that their positive integer multiple indices contains a number which is divisible by that prime number or contains a number whose lowest prime divisor is less than or equal to n/(prime number whose indices is a multiple of).
## Solution
#include <bits/stdc++.h>
using namespace std;

#define int long long
#define vi vector<int>
#define pb(x) push_back(x)
#define vvi vector<vector<int>>
#define vii vector<pair<int , int>>
#define pii pair<int , int>
#define vc vector<char>
#define rep(i , a , b) for(int i=a;i<b;i++)
#define ff first
#define ss second
#define all(x) ((x).begin() , (x).end())
#define input(x) for(auto &i : x)cin >> i
#define si set<int>
#define msi multiset<int>

const int N = 1e3 + 2 , MOD = 1e9 + 7;


signed main()
{
  ios::sync_with_stdio(false);
  cin.tie(nullptr);
  
    int n;
    cin>>n;
    vector<bool> pr(n+1, true);
pr[0] = pr[1] = false;
vi count(n+1,INT_MAX);
for (int i = 2; i * i <= n; i++) {
    if (pr[i]) {
        count[i]=i;
        for (int j = i * i; j <= n; j += i){
            pr[j] = false;
            count[j]=min(count[j],i);
    }
    }
}
    vi v(n);
    input(v);
    vector<bool> ans(n+1,false);
    for(int i=0;i<n;i++){
        if(pr[i+1]&&i>0){
            for(int j=i;j<n;j+=i+1){
                if(v[j]%(i+1)== 0 || (i+1)*count[v[j]]<=n){
                    ans[v[j]]=true;
                }
            }
        }
        else if(i == 0&&v[i] == 1){
            ans[v[i]]=true;
        }
    }
    int a=0;
    for(int i=1;i<=n;i++){
        if(ans[i]== false){
            a++;
        }
    }
    if(a>0){
        cout<<"NO"<<endl;
    }
    else{
        cout<<"YES"<<endl;
    }


  

   return 0;
} 