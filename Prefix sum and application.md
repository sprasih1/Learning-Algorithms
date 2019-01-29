###Prefix Sum array
###Application in competitive programing
1. EQUILIBRIUM INDEX OF A N ARRAY:
(Exclude the index value)

long sum=0;
long a[]=new long[n];
for(int i=0;i<n;i++)
{
sum+=a[i];
}
long leftsum=0;
for(int i=0;i<n;i++)
{
sum-=a[i];
if(leftsum==sum)
{
System.out.println(i);
break;
}
leftsum+=a[i];
}

