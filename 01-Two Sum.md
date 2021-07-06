[Two Sum](https://leetcode-cn.com/problems/two-sum/) <br>

**问题描述：给定一个整数数组 nums 和一个整数目标值 target，请你在该数组中找出和为目标值 target 的那两个整数，并返回它们的数组下标。**<br>

<font face="斜体" color=red size=8>解析：要返回数组下标，不能对数组进行排序，不然还需要额外保存原数组数据及对应下标。此题使用map结构，数组数据的值为key,对应下标作为value，循环nums数组，并在map结构中查找是否存在target - nums[i]数据，存在，则返回map对应key的value值及当前访问的nums数据下标。</font>
<br>
**时间复杂度：遍历一遍nums数组，因此为O(n);**<br>
**空间复杂度：新增map结构，保存对应数据及其下标，

<pre name="code" class="c++">
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        if (nums.size() < 2) {
            return {};
        }
        map<int, int> temp;
        for (int i = 0; i< nums.size(); i++ )
        {
            map<int,int>::iterator it = temp.find(target - nums[i]);
            if (it != temp.end()) {
                return {it->second, i};
            }
            temp[nums[i]] = i;
        }
        return {};
    }
};
</pre>
