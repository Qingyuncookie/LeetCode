# 问题
给定一个数组A，找到其中所含的等差数列片的数目。等差数列片的要求：所含数字数目不小于3，在数组A中连续，相邻数字差值相等。
# 代码
```c
int numberOfArithmeticSlices(vector<int>& A)
{
    int sum=0,count=1;
    if(A.size()<3) return 0;
    for(int i=1;i<A.size()-1;i++)
    {
       if(A[i]-A[i-1]==A[i+1]-A[i])   
       sum+=(count++);
       else
       count=1;
    }
    return sum;
}
```
# 总结
注意count++的返回值为count。sum+=(count++)巧妙！
