# 问题
找零钱问题，卖家只能从买家手里获取零钱。
# 代码
```c
bool lemonadeChange(vector<int>& bills) {
    int five=0,ten=0,twenty=0;
    for(int i=0;i<bills.size();i++)
    {
        if(bills[i]==5)five++;
        else if(bills[i]==10)
        {
            if(five>0)
            {
                five--;
                ten++;
            }
            else
                return false;
        }
        else
        {
            if(five<1)return false;
            if(ten>0)
            {
                    five--;
                    ten--;
                    twenty++;
            }
            else if(five>=3)
            {
                five-=3;
            }
            else
                return false;
        }
    }
    return true;
}
```
# 总结
注意是按照顺序来确定是否可以找零。
