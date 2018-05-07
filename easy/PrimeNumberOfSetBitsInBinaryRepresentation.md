# 问题
判断所有介于L和R之间的数的二进制表示中1的个数是质数的个数。
# 代码
```c
bool isprime(int t)
{
   if(t==1) return false;
   for(int i=2;i<=sqrt(t);++i)
   {
       if(t%i==0) return false;
   }
   return true;
}
 int countPrimeSetBits(int L, int R)
 {
     int res=0;
     for(int n=L;n<=R;++n)
     {    
       int count=0;
         int j=n;
       while(j)
         {
            count += j&1;
            j >>= 1;
         }
         if(isprime(count)) ++res;
     }
     return res;  
 }
```
# 总结
两个点需要注意，一个是判断二进制中1的个数，一个是判断这个数是否为素数。
