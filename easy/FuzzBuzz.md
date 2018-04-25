# 问题
将数字1-n输出为字符类型；若为3的倍数，输出为"Fuzz",若为5的倍数，则输出"Buzz",若两者都满足，则输出"FizzBuzz"。
# 代码
```c
vector<string> fizzBuzz(int n)
{
   int i=0;
   vector<string> ret_vec(n);
   for(int i=1;i<=n;++i)
   {
      if((i%3==0)&&(i%5!=0)) ret_vec[i-1]+="Fizz";
      if((i%5==0)&&(i%3!=0)) ret_vec[i-1]+="Buzz";
      if((i%3==0)&&(i%5==0)) ret_vec[i-1]+="FizzBuzz";
      if(ret_vec[i-1].empty())
      {
          stringstream ss;
          ss<<i;
          ret_vec[i-1]+=ss.str();
      }
   }
   return ret_vec;
}
```
# 总结
类型转换，整数型转换为字符型，使用stringstream。如BaseballGame一题。
