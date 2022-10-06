# *Fibonnaci Sequence*


![Fibonnaci](https://user-images.githubusercontent.com/114954706/193700679-d99ae2df-baff-4d49-8606-967845da04dc.png)![Sequence](https://user-images.githubusercontent.com/114954706/194399272-93807380-ea69-4d1d-84b5-ebabe200812f.png)



## **Abdulrhman Shawky**  

#### [MyProfile.Github](https://github.com/AbdulrahmanGhitani)


-----------------------
### 1. ==First Solution== {#1st} 

```c++
#include "iostream"
using namespace std;
void main()
{
    long long n1(0),n2(1),x(0);
    int n3(0);

    cout<<"Enter n"<<endl;
    cin>>n3;
    if(n3<2)
        cout<<n3<<endl;
    else
    {
        for (int i=2 ; i<=n3 ;i++)
        {
            x=n1+n2;
            n1=n2;
            n2=x;
        }
        cout<<x<<endl;
    }
    return 0;   
}
```

### 2. ==Second Solution== {#2st}

```c++
#include iostream
using namespace std;
long long fibo(int n)
{
  if (n<2)
      return n;

  return fibo(n-1)+fibo(n-2);
}
int main()
{
int n;
cout<<"Enter n"<<endl;
cin>>n;
cout<<fibo(n);
    return 0;
}
```


### 3. ==Thired Solution== {#3st}
```c++
#include "iostream"
using namespace std;

long long fibo(int n)
{
    long long f[n+2];
    f[0]=0;
    f[1]=1;
    for(int i=2;i<=n;i++)
        {
           f[i]=f[i-1]+f[i-2];
        }
    return f[n];
}
int main()
{
    int n;
    cout<<"Enter n"<<endl;
    cin>>n;
    cout<<fibo(n);
    return 0;
}
```


### 4. ==Fourth Solution== {#4st}
```c++
#include <iostream>
using namespace std;

long fibo(int n) ;

int main()
{
    int n;
    cout<<"Enter n"<<endl;
    cin >> n;
    cout << fibo(n);
}
long f[1000]={0};
long fibo(int n )
{
    if(n==0)
        return 0;

    if(n==1||n==2)
        return (f[n]=1);

     if (f[n])
        return f[n];

    int k = (n % 2 == 0) ? n/2 : (n+1) / 2;

    f[n]= (n%2==0)? (2*fibo(k-1) + fibo(k))*fibo(k)  :  fibo(k)*fibo(k)+fibo(k-1)*fibo(k-1);
    return f[n];
}
```
### 5. ==Fifth Soluation== {#5st} 
```c++

#include "iostream"
using namespace std;
void multiply_arr(long long f[2][2], int m[2][2])
{
    long long a=f[0][0]*m[0][0]+f[0][1]*m[1][0];
    long long b=f[0][0]*m[0][1]+f[0][1]*m[1][1];
    long long c=f[1][0]*m[0][0]+f[1][1]*m[1][0];
    long long d=f[1][0]*m[0][1]+f[1][1]*m[1][1];

    f[0][0]=a;
    f[0][1]=b;
    f[1][0]=c;
    f[1][1]=d;
}

void calc_pow(long long f[2][2],int n)
{
    int m[2][2]={1,1,1,0};
    for(int i=1;i<n;i++)
    {
        multiply_arr(f,m);
    }
}

long long fibo(int n)
{
    long long f[2][2]={1,1,1,0};
    if(n==0)
        return 0;
    calc_pow(f,(n-1));

    return f[0][0];
}
int main()
{
    int n;
    cout<<"Enter n"<<endl;
    cin>>n;
cout<<fibo(n);
   return 0;
}
```

### 6. ==Six Solution==  ^[There may be a small error in the large numbers] {#6st}

```c++
#include<iostream>
#include<cmath>
using namespace std;
long long fibo(int n) {
     double x = (1 + sqrt(5)) / 2;
    return round (pow(x, n) / sqrt(5));
}

int main ()
{
    int n ;
    cout<<"Enter n"<<endl;
    cin>>n;
    cout << fibo(n) << endl;
    return 0;
}
```




|| Time Complexity|**Space**|
|:------|:------:|-------|
|[First Solution](#first-solution) | **O(n)**||
|[Second Solution](#2st)|**O(2^n^)**||
|[Thired Solution](#3st)|**O(n)**||
|[Fourth Solution](#4st)|**O(log(n)**||
|[Fifth Solution](#5st)|**O(n)**||
|[Sex Solution](#6st)|**O(log(n))**||



## What is your best solution? 
- [ ] First Solution
- [ ] Second Solution
- [ ] Third Solution
- [ ] Fourth Solution
- [ ] Fifth Solution
- [ ] Sixth Solution