题目：
283. 移动零

给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

请注意 ，必须在不复制数组的情况下原地对数组进行操作。
示例 1:
输入: nums = [0,1,0,3,12]
输出: [1,3,12,0,0]
示例 2:
输入: nums = [0]
输出: [0]
解题思想：
定义左右指针都先指向第一个元素，当右指针指向元素为0则向右移动右指针；
直到右指针指向元素不为零则交换左右指针指向的元素，左指针向右移动一位，
然后继续向右移动右指针直达右指针不为零，循环；
右指针遍历完数组长度结束。

保证【0，left]内元素都不为0，【left,right]内元素都为0.
快速排序思想不能保证相对顺序。
代码：
class Solution {
    public void moveZeroes(int[] nums) {
        int left=0;
        for(int right=0;right<nums.length;right++){
            if(nums[right]!=0){ //Java语法严格，int不能自动转为boolean
                int tmp=nums[right];
                nums[right]=nums[left];
                nums[left]=tmp;
                left++;
            }
        }
        
    }
}
