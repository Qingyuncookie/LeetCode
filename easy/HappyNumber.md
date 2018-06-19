# 问题
给定一个整数，判断其是否为快乐数字。如果每一位上数字的平方和经多次循环后可得到1，则为快乐数字。
# 代码
```c
bool isHappy(int n)
{
    std::unordered_set<int> record;
    while (true)
    {
        int sum = 0;
        while (n > 0)
        {
            int digit = n % 10;
            n /= 10;
            sum += digit * digit;
        }

        if (sum == 1)
        {
            return true;
        }

        if (record.find(sum) != record.end())
        {
            return false;
        }
        else
        {
            record.insert(sum);
        }

        n = sum;
    }

    return false;        
}
```
# 总结
将出现的每一个平方和数字储存起来如果在得到1之前再次出现，则输出false若输出1则输出true。
