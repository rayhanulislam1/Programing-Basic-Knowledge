<h1 align="center">Standard Template Library (STL)</h1>

Array:
```c++
int arr[10] = {1, 12, 3, 24, 35, 16};  
   sort(arr, arr+10, [](int i, int j){  
       return i > j;  
   });   
   F0R(i, 10){  
       cout << arr[i] << " ";  
   }
```
String:
```c++
string s1 = str.substr(0, i);	  // 0 = index_start, i = length
string s2 = str.substr(i, x-i);  // i = index_start, x-i = length
```
Stack:
```c++
stack <int> s; // LIFO = last in  first out
   s.push(10); // s = [10]
   s.push(20); // s = [10, 20]
   s.push(30); // s = [10, 20, 30]
   cout << s.size() << en;
   while (not s.empty()){
       cout << s.top() << en;
       s.pop();
   }
   cout << s.empty() << en;
```
Set & MultiSet:
```c++
set <int> s; // Red Black Tree
    s.insert(10);
    s.insert(20);
    s.insert(3);
    s.insert(5);
    for(auto it : s){
       cout << it << " ";
    }cout << en;
    auto it = next(s.begin(), 2);
    auto it1 = prev(s.begin(),3);
    auto it2 = s.find(5);
    auto it3 = next(s.find(10), 1);
    auto it4 = s.find(-1);
    cout << *it4 << en;
```c++
multiset <int> m;
    m.insert(2);
    m.insert(4);
    m.insert(3);
    m.insert(4);
    m.insert(5);
    auto it = m.find(4);
    m.erase(it);
    for(auto it : m){
       cout << it << en;
    }
```
### Queue:
```c++
queue <int> q; // FIFO = First in First Out
   q.push(10);
   q.push(20);
   q.push(30);
   while (!q.empty()){
       cout << q.front() << en;
       q.pop();
   }
   cout << q.empty() << en;
```
```c++
priority_queue <int> q;
    q.push(3);
    q.push(12);
    q.push(-1);
    q.pop();
    cout << q.top() << en;
```
Dequeue: 
```c++
deque <int> q;
   q.push_front(10);
   q.push_front(20);
   q.push_back(21);
   q.push_back(12);
   q.pop_front();
   q.pop_back();
   for(int i:q){
       cout << i << endl;
   }
```
Lambda Functions:
```c++
auto func = [] (int i, int j){
   return i+j;
  };
  cout << func(10, 20) << endl;
```c++
function <int(int)> fib = [&] (int i){
       if(i <= 1) return 1;
       return fib(i-1) + fib(i-2);
   };
   cout << fib(4);
```
 MAP:
```c++
map <String, int> freq;
for(int i = 0; i < n; i++){
   string s;
   cin >> s;
   freq[s]++;
}
for(auto it : freq){
   cout << it.first << " " << it.second << en;
}
```
```c++
map <int , vector<int>>  m;
int x = m[a].size();
int y = m[b].size();
int mi = min(mi, m[a][0]);
int ma = min(ma, m[b][y-1]);
```c++
if(ind.count(ans)){
   return {ind[ans], i};
}
```
```c++
n*(n - 1) = 10 ?  { N = 5, arr[n] = 1 1 1 1 1 -> 1 2 3 4 5}
```
Euclidean Algorithm:
```c++
int gcd(int a, int b) {
if (a == 0) return b;
return gcd(b % a, a);
}
lcm(a, b) = a*b/(__gcd(a, b);
```
Binary Exponentiation:
```c++
int power(int a, int b){
    int res = 1;
    while(b > 0){
        if(b%2 == 1){
            res = res * a;
            res %= MOD;
            b--;}
        a = a * a;
        a %= MOD;
        b /= 2;
    }
    return res;
}
```
Binary Search : O(log n)
```c++
int binary_search(int arr[], int n, int x){
    int left = 0, right = n - 1, mid;
    while(left <= right){
        mid = left + (right - left)/2;
        if(arr[mid] == x) return mid;
        if(arr[mid] < x) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}
```
Grap_Theoury
DFS:
```c++
void dfs(int node){
    vis[node] = 1;
   for(int next : g[node]){             // for(int i = 1; i <= n; i++)
       if(!vis[next]){
           dfs(next);
       }
   }
}
```
```c++
vector < pair <int, int> > v[1000];
void solve(int tt){
   ll n, m;
   cin >> n >> m;
   for(ll i = 1; i <= m; i++){
       ll x, y, w;
       cin >> x >> y >> w;
       v[x].push_back({y, w});
       v[y].push_back({x, w});
   }
   for(auto [u, w] : v[1]){
      cout << u << " " << w << " ";
   }
   cout << v[2].size() << en;
}
```
```c++
vector < ll > v[N];
bool vis[N];
vector < ll > ans;
 
void dfs(ll node){
   if(vis[node] == 1) return;
   ans.push_back(node); // somehow connected to node a
   vis[node] = 1;
   for(auto u : v[node]){
       dfs(u);
   }
   return;
}
void solve(int tt){
   ll n, m; // n = node count, m = edge count
   cin >> n >> m;
   mem(vis, 0); // vis[i] = 0
   for(int i = 1; i <= m; i++){
       ll x, y;
       cin >> x >> y; // input edges
       v[x].push_back(y);
       v[y].push_back(x);
   }
   ll a; cin >> a;
   dfs(a);
 
   for(auto u : ans){
       cout << u << en;
   }
}
```
BFS:
```c++
void solve(int tt){
   int n, m;
   cin >> n >> m;
   vector < vector <int>> v(n);
   for(int i = 0; i < m; i++){
       int a, b; cin >> a >> b;
       a--, b--;
       v[a].push_back(b);
   }
   queue <int> q;
   vector <int> dis(n);
   vector <bool> visit(n, false);
 
   int st = 0;
   q.push(st);
   dis[st] = 0;
   while(!q.empty()){
       int nd = q.front();
       q.pop();
       for(int x : v[nd]){
           if(visit[x]) continue;
           visit[x] = true;
           dis[x] = dis[nd] + 1;
           q.push(x);
       }
   }
   for(int x : dis) cout << x << " "; cout << en;
}
```
Dijkstra’s:
```c++
void solve(int tt){
   int n, m;
   cin >> n >> m;
   vector < vector < pair<int, int >>> v(n);
   for(int i = 0; i < m; i++){
       int a, b, w; cin >> a >> b >> w;
       a--, b--;
       v[a].push_back({b, w});
   }
   vector <long long> dis(n, 1e18);
   vector <bool> visit(n, false);
   priority_queue < pair < long long, int>, vector <pair <long long, int >> , greater <pair <long long, int>>> pq;
  
   int st = 0;
   pq.push({0, st});
   dis[st] = 0;
 
   while(!pq.empty()){
       int nd = pq.top().second;
       pq.pop();
       if(visit[nd]) continue;
       visit[nd] = true;
       for(auto [x, w] : v[nd]){
           if(dis[nd] + w < dis[x]){
               dis[x] = dis[nd] + w;
               pq.push({dis[x], x});
           }
       }
   }
   for(auto x : dis) cout << x << " "; cout << en;
}
```
Dynamic Programing:
```c++
// Fibonacci Series
int dp[105];
int f(int n){
   if(n == 0) return 0;
   if(n == 1) return 1;
   if(dp[n] >= 0) return dp[n];
   dp[n] = f(n-1) + f(n-2);
   return dp[n];
}
void solve(int tt){
   for(int i = 0; i < 105; i++) dp[i] = -1;
   cout << f(7) << en;
}
```
Sieve & Prime Factorization: N(log N):
```c++
const int N = 10000000;
vector <int> low(N+1), pm;
void sieve(){
    for(int i = 2; i <= N; i++)
        low[i] = i;
    for(int i = 2; i * i <= N; i++){
        if(low[i] == i)
            for(int j = 2 * i; j <= N; j += i)
                if(low[j] == j)
                    low[j] = i;
    }
}
vector <int> prime_fact(int x){
        vector <int> res;
        while(x > 1){
            res.push_back(low[x]);
            x /= low[x];
        }
        return res;
}
```
Sieve Of Eratosthenes: N(√N)
```c++
const int n = 100000
bool prime[1000000];
vector <int> p;
void sieve(int n){
   for(ll i = 3; i*i <= n; i+=2){
       if(prime[i] == false){
           for(ll j = i*i; j <= n; j+=i)prime[j] = true;
       }
   }
   p.push_back(2);
   for(int i = 3; i <= n; i+=2) if(prime[i] == false) p.push_back(i);
   for(int i = 0; i < p.size(); i++)  cout << p[i] << " ";
}
```
Big Mod:
```c++
int power(ll a, ll b, ll mod){
       if(b == 0) return 1%mod;
       ll tmp = power(a, b/2, mod);
       ll result =( tmp*tmp)%mod;
       if(b%2 == 1) result = (result*a) % mod;
       return result;
   }
```
Bitwise Operation:
```c++
    Bitwise XOR:
   	 5 = 0 1 0 1 
   	 6 = 0 1 1 0
    5^6 = 0 0 1 1
    Left Shift: left_shift * 2
      x << = 0 1 1 0 1 0 1 1
    x << 2 = 1 1 0 1 0 1 0 0
    Right Shift: Right_shift / 2
      x >> = 0 1 1 0 1 0 1 1
    x >> 2 = 0 0 0 1 1 0 1 0
```
Pointer:
```c++
void call(int *x){
   *x = 20;
   cout << *x << en;
}
int main(){
   int n = 10;
   call(&n);
   cout << n << en;
   return 0;
}
```
```c++
int a = 10, b = 20;
   vector <int*> v;
   v.push_back(&a);
   v.push_back(&b);
   *v[0] += 1;
   cout << a << en;
```
Random Number:
```c++
srand(clock());
int a = rand()%10+1;
```
Wrong Submission
```c++
cout << fixed << setprecision(10) << sum << endl;srand(clock());
```
```c++
value = (pow(3, 4) + 0.5)
```
```c++
int min  = INT_MIN, max = INT_MAX;
```
```c++
char ch[26];
while (scanf("%s",ch) != EOF)
```
```c++
 < input.txt > output.txt
```
```c++
C & C++
+) Loop:  i) Initialization (i=0);   ii) Terminate if(i<10);  iii) Increment/Decrement (i=i+1;)
+) Library Function:  pow(), strlen(), strcpy(), strrev(), strupr(), strlwr(), strcmp(), strcat()
+) int num;  scanf("%4d", & num);	printf("%d\n",num);
+) double num;  scanf("%lf", & num);	printf("sum is= %0.3lf\n",sum);
+) float num; scanf("%f", & num);   printf("%f\n",num);
+) char n;    scanf("%c", & n);	printf("%c\n",n);
+) char str[]; int l;     l = strlen(str);   scanf("%s", & str);	printf("%s\n",str);
+) char s[100];  scanf("%s",s);	printf("%s\n",s);
+) long long int n; scanf("%lld", &n);	printf("%lld", n);
+) scanf("%[^\n]",str);
+) fflush(stdin);  gets(person[i].name);
```

