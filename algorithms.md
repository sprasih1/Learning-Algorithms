#### Matrix Exponentiation:
Used to calculate fibonacci and other sequences in O(log n)
let F(n) be nth fibonacci number.
    Then F(n) = F(n-1) + F(n-2)
    In matrix representation :
    
       First matrix   =   Second matrix  *  Third matrix
       
       | F(n)   |     =    | 1     1 |    * | F(n-1) |
       
       | F(n-1) |     =    | 1     0 |    * | F(n-2) |
       
    Implementation:
    
    /* function that returns nth Fibonacci number */
       int fib(int n)
       {
         int F[2][2] = { {1,1} , {1,0} };
         if (n == 0)
           return 0;
         power(F, n-1);
         return F[0][0];
       }

       /* Optimized version of power() is also there in dynamic programming*/
       void power(int F[2][2], int n)
       {
         if( n == 0 || n == 1)
             return;
         int M[2][2] = { {1,1} , {1,0} };

         power(F, n/2);
         multiply(F, F);

         if (n%2 != 0)
            multiply(F, M);
       }

       void multiply(int F[2][2], int M[2][2])
       {
         int x =  F[0][0]*M[0][0] + F[0][1]*M[1][0];
         int y =  F[0][0]*M[0][1] + F[0][1]*M[1][1];
         int z =  F[1][0]*M[0][0] + F[1][1]*M[1][0];
         int w =  F[1][0]*M[0][1] + F[1][1]*M[1][1];

         F[0][0] = x;
         F[0][1] = y;
         F[1][0] = z;
         F[1][1] = w;
       }


###### Other way to find nth fibonacci number

#include <iostream>
using namespace std;

#define long long long
const long M = 1000000007; // modulo
map<long, long> F;

long f(long n) {
	if (F.count(n)) return F[n];
	long k=n/2;
	if (n%2==0) { // n=2*k
		return F[n] = (f(k)*f(k) + f(k-1)*f(k-1)) % M;
	} else { // n=2*k+1
		return F[n] = (f(k)*f(k+1) + f(k-1)*f(k)) % M;
	}
}

main(){
	long n;
	F[0]=F[1]=1;
	while (cin >> n)
	cout << (n==0 ? 0 : f(n-1)) << endl;
}
The complexity of above code is O(log n* log log n)


######Sieve of Eratosthenes : 
Given a number n, find all primes smaller than or equal to n.
