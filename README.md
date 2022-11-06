# LeetCode  ![leetcode](https://user-images.githubusercontent.com/98816824/200170845-dfc5c614-3f1c-4450-a005-9871435b84c1.png)

记录自己刷题日常（争取每天刷上几道）由于自己基础还不太好，所以先刷简单题

![C语言](https://img.shields.io/badge/%E5%B8%B8%E7%94%A8%E8%AF%AD%E8%A8%80-C-blue)
![JAVA](https://img.shields.io/badge/%E5%B8%B8%E7%94%A8%E8%AF%AD%E8%A8%80-Java-critical)

# **目录**
 ## 算法
   * 算法入门
     |      Day    | topic1 | topic2 | 3 |
     | :-----------: | :-----------: | :-----------: | :-----------: |
     |    Day1     | [704 二分查找](#704) | [278 第一个错误版本](#278) | [35 搜索插入位置](#35) |
     |    Day2     | null        | null | null |
 

***

## 算法
 ### 算法入门
 #### DAY 1
 
 <a id = "704"></a>
     
  * [704 二分查找](https://leetcode.cn/problems/binary-search)`Java` 时间:0ms  内存:41.8 MB
     ```java
        class Solution {
          public int search(int[] nums, int target) {
            int low=0;//数组的第一位
            int high=nums.length-1;//数组的第二位
            while(low<=high){
                int mid=(high-low)/2+low;//用于查找数组的中间值
                int num=nums[mid];//储存中间值
                if(num==target)
                    return mid;
                else if (num>target)
                    high=mid-1;
               else
                    low=mid+1;
             }
            return -1;
           }
         }
     ```
     
 <a id = "278"></a>
     
   * [278 第一个错误的版本](https://leetcode.cn/problems/first-bad-version)`Java` 时间:13 ms  内存:38.2 MB
      ```java
      /* The isBadVersion API is defined in the parent class VersionControl.
      boolean isBadVersion(int version); */

      public class Solution extends VersionControl {
          public int firstBadVersion(int n) {
             int low=1;
             int hight=n;
             while(low<hight){ 
                 int mid=low+(hight-low)/2;
                 if(isBadVersion(mid))
                     hight = mid;//答案在区间 [low, mid] 中
                 else
                     low = mid+1;//答案在区间 [mid+1, hight] 中
                }
                return low;// 此时有 low == hight，即所求答案
              }
            } 
      ```
 
  <a id = "35"></a>
 
   * [35 搜索插入位置](https://leetcode.cn/problems/search-insert-position)`Java` 时间:0 ms  内存:41.1 MB
      ```java
          class Solution {
            public int searchInsert(int[] nums, int target) {
              int low=0;
              int high=nums.length-1;
               while(low<=high){
                  int mid=(high-low)/2+low;
                  if(nums[mid]==target)
                      return mid;
                  else if(nums[mid]>target)
                      high=mid-1;
                  else 
                      low=mid+1;
                  }
                  return low; //当查询不到时返回low
                              //因为前面的if条件，low的值始终比给定值小，即low为按顺序插入的位置
                }
            }
      ```
      
      
      
      
      
      
      
      
      
