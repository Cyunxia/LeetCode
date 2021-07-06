**问题描述：给定一个整数数组 nums 和一个整数目标值 target，请你在该数组中找出和为目标值 target 的那两个整数，并返回它们的数组下标。**

**解析：**

'''
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
'''
