Given an array Arr of N positive integers. Your task is to find the elements whose value is equal to that of its index value ( Consider 1-based indexing ).

![](/images/valueEqualToidx.PNG)
<hr>

Solution

```
	vector<int> valueEqualToIndex(int arr[], int n) {
	    vector<int> ans;
	    for(int i=0;i<n;i++){
	        if(arr[i] == i+1){
	            ans.push_back(i+1);
	        }
	    }
	    return ans;
	}
```

Time complexity: O(N). 
One linear traversal, so time complexity is O(N).

Space Complexity: O(1). 
As no extra space is required(we are not considering the auxiliary vector).