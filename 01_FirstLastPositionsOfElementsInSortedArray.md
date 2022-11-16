Given a sorted array arr containing n elements with possibly duplicate elements, the task is to find indexes of first and last occurrences of an element x in the given array.

![](/images/firstLastidx.PNG)
<hr>

Solution 1


```
vector<int> find(int arr[], int n , int x ){
    if(binary_search(arr,arr+n,x)){
        int firstIdx = lower_bound(arr,arr+n,x)-arr;
        int lastIdx = upper_bound(arr,arr+n,x)-arr;
        return {firstIdx, lastIdx-1};
    }
    return {-1,-1};
}
```
Time Complexity : O(log(n))

Space Complexity : O(1)

<hr>

Solution 2

```
class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        int firstIdx = -1;
        int lo = 0;
        int hi = nums.size() - 1;
        while(lo <= hi){
            int mid = lo + (hi - lo)/2;
            if(nums[mid] == target){
                firstIdx = mid;
                hi = mid- 1;
            }
            else if (nums[mid] < target){
                lo = mid + 1;
            }
            else{
                hi = mid -1;
            }
        }
        
        int lastIdx = -1;
        lo = 0, hi = nums.size() -1;
        while(lo <= hi){
            int mid = lo + (hi - lo)/2;
            if(nums[mid] == target){
                lastIdx = mid;
                lo = mid + 1;
            }
            else if (nums[mid] < target){
                lo = mid + 1;
            }
            else{
                hi = mid -1;
            }
        }
        return {firstIdx, lastIdx};
    }
};
```

TC : O(log(n))

SC : O(1)