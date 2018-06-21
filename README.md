# Tutorials-Cup
Some Solutions of the site Tutorials Cup! Hope it helps...
The template used for the codes...

**
	* Author   : Rohit Kumar Kerketta
**/
```
#include <bits/stdc++.h>
using namespace std;
typedef unsigned long long ull;
typedef long double ldb;
typedef long long int ll;
#define pb    		    push_back
#define For1(i,a,n)  	for (i = (a); i<(n); i++)
#define For2(j,a,n)  	for (j = (a); j<(n); j++)
#define For3(k,a,n)  	for (k = (a); k<(n); k++)
#define For1e1(i,a,n)  	for (i = (a); i<=(n); i++)
#define For2e2(j,a,n)  	for (j = (a); j<=(n); j++)
#define For3e3(k,a,n)  	for (k = (a); k<=(n); k++)
#define ForMap(it,mp)  	for (it = mp.begin();it!=mp.end();it++)

#define For1r(i,a,n)  	for (i = (a); i>(n); i--)
#define For2r(j,a,n)  	for (j = (a); j>(n); j--)
#define For3r(k,a,n)  	for (k = (a); k>(n); k--)
#define For1e1r(i,a,n)  for (i = (a); i>=(n); i--)
#define For2e2r(j,a,n)  for (j = (a); j>=(n); j--)
#define For3e3r(k,a,n)  for (k = (a); k>=(n); k--)

#define SortA(n,x) 	    sort(n,n+x);
#define SortV(s)  	    sort(s.begin(), s.end());
#define SortVR(s)  	    sort(s.rbegin(), s.rend());
#define Search(s)       s.begin(), s.end()
#define SortDec(n)	    sort(n.begin(), n.end(), greater<int>());
#define inp(a) 	        cin>>a;
#define	inStr(a)	    getline(cin,a);
#define Size(a)		    a.size()
#define inp2(a,b)	    cin>>a>>b;
#define inp3(a,b,c)	    cin>>a>>b>>c;
#define inp4(a,b,c,d)   cin>>a>>b>>c>>d;
#define Unique(n)       sort(Search(n)),n.erase(unique(Search(n)),n.end())
#define PI 	            3.1415926535897932384626433832795l
#define Ignore	        cin.ignore();
#define pf(n)		    cout<<n
#define nl				endl;
#define sp				" "
#define mem(n,i)        memset(n,i,sizeof n);
#define deci(n)         cout<<fixed<<setprecision(n);
#define square(n)       n*n
#define cube(n)         n*n*n
#define F               first
#define S               second
#define bug()		    cout<<"*****<>*****\n";
#define s1(n) 			scanf("%d",&n)
#define s2(n,k)			scanf("%d %d",&n,&k)
#define s3(a,b,c)		scanf("%d %d %d",&a,&b,&c)
#define s4(n,k,a,b)		scanf("%d %d %d %d",&n,&k,&a,&b)
#define mp(x,y) 		make_pair(x,y);
#define F				first
#define S				second
#define MP				make_pair
#define ForMp(it,mp)	for(it = mp.begin();it!=mp.end();it++)
typedef stringstream SS;
typedef vector<string> VS;
typedef vector<ll> VLL;
typedef vector<ull> VULL;
typedef vector<int> VI;
typedef vector<char> VC;
typedef map<string, string> MSS;
typedef map <ll,string> MLLS;
typedef map <char,ll> MCLL;
typedef map <string,ll> MSLL;
typedef map<double,ll> MDLL;
typedef map <ll,ll> MLLLL;
typedef pair<int, int> pii;
template <typename T> inline T ItoS(T n){SS a; a<<n;return a.str();}
template <typename T> inline T GCD(T a,T b)   {ll t;while(a){t = a;a = b%a;b = t;}return b;}
template <typename T> inline T TrailingZeros(T  n){ll cnt = 0;for(ll i=5; n/i>=1; i*=5) cnt += n/i;return cnt;}
template <typename T> inline T binary_decimal(T n){ll decimal=0, i=0, rem;while (n!=0){rem = n%10;n/=10;decimal += rem*pow(2,i);++i;}return decimal;}
template <typename T> inline T lcm(T a,T b){return (a*b)/GCD(a,b);}
template <typename T> inline T maxi(T x, T y) { if(x>y) return x; else return y;}
template <typename T> inline T maxi(T x, T y,T z) { return maxi(maxi(x,y),z);}
template <typename T> inline T mini(T x, T y) { if(x<y) return x; else return y;}
template <typename T> inline T mini(T x, T y,T z) { return mini(mini(x,y),z);}
template <typename T> inline T Pow(T base,T exp){ll result = 1;while (exp){if(exp&1)result*=base;exp>>=1;base*=base;}return result;}
template <typename T> inline T Mulmod(T a, T b, T c){ull x = 0,y = a%c;while(b>0){if(b&1) x = (x+y)%c;y = (y<<1)%c;b >>= 1;}return x;}
template <typename T> inline T Pow(T base,T exp,T mod){ull x = 1, y = base;while(exp>0){if(exp&1) x = Mulmod(x,y,mod);y = Mulmod(y,y,mod);exp >>= 1;}return x;}
template <typename T> inline T modulo(T a,T b,T c){ull x = 1 , y = a%c ;while( b>0 ){if(b%2) x = Mulmod(x,y,c) ;y=Mulmod(y,y,c);b/=2;}return x%c ;}
template <typename T> inline T BigMod(T a, T b, T m){if(!b)return 1;ll x=BigMod(a, b/2, m);x=(x*x)%m;if(b%2)x=(x*a)%m;return x;}
template <typename T> inline T EGCD(T a,T b,T &x,T &y){if(a == 0) {x = 0;y = 1;return b;}T x1, y1;T d = EGCD(b % a, a, x1, y1);x = y1 - (b / a) * x1;y = x1;return d;}
 
/****************** Prime Generator **********************/
 
const int N = 1e7+7; int prime[20000010]; bool isprime[N]; int nprime;
template <typename T> void Sieve(T a){nprime = 0;memset(isprime,true,sizeof(isprime));isprime[1]=false;for(int i=2;i<N;i++){if(isprime[i]){prime[nprime++]=i;for(int j=2;i*j<N;j++)isprime[i*j]=false;}}}
template <typename T> bool miller_rabin(T p, T itt) {if(p<2) return 0 ;if(p==2) return 1;if(p%2==0) return 0 ;ull s = p-1 ;while(s%2==0) s/=2;for(ll i=1;i<=itt;i++) {ull a = rand() % (p-1)+1 , temp = s ;ull mod = modulo(a,temp,(ull)p);while(mod!=1 and mod!=p-1 and temp!=p-1){mod = Mulmod(mod,mod,(ull)p);temp*=2;}if(temp%2==0 and mod!=p-1) return false ;}return true;}
template <typename T> inline T PrimeFactors(T n){ll cnt=0,sum=1;for(int i=0; prime[i]*prime[i]<=n and i<nprime;i++){cnt=0;while(n%prime[i]==0){cnt++;n/=prime[i];}sum*=(cnt+1);}if(n>1)sum*=2;return sum;}
const ll MOD = 10e9+7;
/****************** Geometry *****************/
 
template <typename T> inline T PointDistanceHorVer(T x1,T y1,T x2, T y2) {return abs(x1-x2)+abs(y1-y2);}
template <typename T> inline T PointDistanceDiagonally(T x1,T y1,T x2, T y2) {return sqrt((x2-x1)*(x2-x1) + (y2-y1)*(y2-y1));}
template <typename T> inline T PointDistanceMinimum(T x1,T y1,T x2, T y2) { T tmp1=abs(x1-x2); T tmp2=abs(y1-y2); T tmp3=abs(tmp1-tmp2); T tmp4=min(tmp1, tmp2); return tmp3+tmp4; }
template <typename T> inline T PointDistance3D(T x1,T y1,T z1,T x2,T y2,T z2) {return sqrt(square(x2-x1)+square(y2-y1)+square(z2-z1));}
template <typename T> inline T Cube(T a){return a*a*a;}
template <typename T> inline T RectengularPrism(T a,T b,T c){return a*b*c;}
template <typename T> inline T Pyramid(T base, T height){return (1/3)*base*height;}
template <typename T> inline T Ellipsoid(T r1,T r2,T r3) {return (4/3)*PI*r1*r2*r3;}
template <typename T> inline T IrregualarPrism(T base, T height){return base*height;}
template <typename T> inline T Sphere(T radius){ return (4/3)*PI*radius*radius*radius;}
template <typename T> inline T CylinderB(T base, T height){return base*height;} // base and height
template <typename T> inline T CylinderR(T radius, T height){return PI*radius*radius*height;} // radius and height
template <typename T> inline T Cone (T radius,T base, T height){return (1/3)*PI*radius*radius*height;}
template <typename T> inline void pfArr(T vec){ int i; For1(i,0,vec.size()) cout<<vec[i]<<" "; }
ll max(ll m,ll n){	return (m>n)?m:n;}
ll min(ll m,ll n){	return (m<n)?m:n;}
void pfs(string s){cout<<s;}
vector<ll> inpA(int n){VLL arr(n);int i;For1(i,0,n)cin>>arr[i];return arr;} 
void pfMap(map<ll,ll> mp){map<ll,ll>::iterator it;for(it=mp.begin();it!=mp.end();it++)pf(it->F)<<" "<<it->S<<nl;}
template <typename T1>inline T1 STOI(string s,T1 i){stringstream ss(s);ss>>i;return i;}
char ITOC(ll i){return i+'0';}
string convFactBase(int k){string res = "";int num = 1;while(k){int rem = k%num;char c = ITOC(rem);res += c;k = k/num;num++;}return res;}
/**>>>>>>>>>>>>>>>>>>> END <<<<<<<<<<<<<<<<<<**/
