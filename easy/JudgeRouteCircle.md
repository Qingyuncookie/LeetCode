# 问题
给定上下左右移动操作，判断移动后是否还在原位置。
# 代码
```c
int l=moves.length();
int x=0,y=0;
  for(int i=0;i<l;i++)
  {
     if (moves[i]=='U')y++;
        else if(moves[i]=='D')y--;
          else if(moves[i]=='R')x++;
            else x--;
  }
 if (x==0&&y==0)return true;
     else return false;
```
# 总结
1.moves function.
2.if else 使用。
