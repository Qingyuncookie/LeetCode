# 问题
给定一个字符串，按照其中字符出现的频率排序。
# 代码
string frequencySort(string s)
{
    unordered_map<char, int> m;
    for (char c : s) ++m[c];
    sort(s.begin(), s.end(), [&](char& a, char& b){return m[a] > m[b] || (m[a] == m[b] && a < b);});
    return s;
}
# 总结
unordered_map是一个关联容器，存储key,value，与unordered_set一样，是一个无序集合容器，通过哈希表来组织元素。关联容器中的元素是通过key而不是绝对位置来引用。
