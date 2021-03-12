- 最普通的从小到大排序
```
sort(intervals.begin(), intervals.end())
```
- 直接在sort函数的参数里写规则  
比如：vector<vector<int>> intervals = { {1,2},{3,10},{5,14},{2,10} }  
二维数组按子数组的第二个元素从小到大进行排序
要排列成1,2],[3,10],[2,10],[5,14]
```
sort(intervals.begin(), intervals.end(), [](vector<int>& a, vector<int>& b) {
      return a[1] < b[1];
});
```
                         
- 单独写一个静态函数作为sort函数的一个参数
```
class Solution {
public:
    vector<vector<int>> reconstructQueue(vector<vector<int>>& people) {
        sort(people.begin(),people.end(), sort_rule);
        /..../
    }
        
    static bool sort_rule(vector<int>& a,vector<int>& b){
        if(a[0]==b[0]) return a[1] < b[1];
        else return a[0]>b[0];
    }
}

```
