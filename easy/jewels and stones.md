# 问题分析
J代表珠宝类型，S代表手中的石头类型，判断自己手里的石头有多少个是珠宝。
# 代码
```C
int numJewelsInStones(string J, string S)
 {
     {
     int num=0;
     for(int i=0; i<J.length(); i++)
         {
             for(int j=0; j<S.length(); j++)
             {
                 if (J[i]==S[j])
                 {
                     num++;
                 }
             }
         }

     return num;
     }   
 }
 int main()
 {
         char J[50],S[50];
         cout << "请输入钻石J：";
         cin >>J;
         cout <<"请输入石头S：";
         cin >>S;
        cout << endl << numJewelsInStones(J, S);
   return 0;
 }
```
# 总结
1.size() 一般用作返回容器大小的方法，
  length() 一般用作返回一个序列的长度，
  上述两者结果一样。
  sizeof()用来求变量的空间大小。
2.for循环的使用。
