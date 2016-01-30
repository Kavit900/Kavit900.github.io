---
layout: post
date: 2016-01-30
title: Next Permutation
---

Next permutation is a concept, which rearranges numbers into lexicographically next greater permutation of numbers.

If such arrangement is not possible, it must rearrange it as the lowest possible order(i.e sorted in ascending order).

The condition provided is replacement must be in-place and do not allocate extra memory space.

## Algorithm

1. Scan from right to left, find the element that is less than it's previous one.

```
4 5 6 3 2 1
  |
  p
```

2. Scan from right to left, find the first element that is greater than p.

```
4 5 6 3 2 1
    |
    q
```

3. Swap p and q now.
```
4 5 6 3 2 1
swap
4 6 5 3 2 1 
```

4. Reverse the elements from [p+1, length-1];

### Code in Java

```python
public int[] nextPermutation(int[] nums) {
    if(nums == null || nums.length<2)
        return;
 
    int p=0;            
    for(int i=nums.length-2; i>=0; i--){
        if(nums[i]<nums[i+1]){
            p=i;
            break;
        }    
    }
 
    int q = 0;
    for(int i=nums.length-1; i>p; i--){
        if(nums[i]> nums[p]){
            q=i;
            break;
        }    
    }
 
    if(p==0 && q==0){
        nums = reverse(nums, 0, nums.length-1);
        return nums;
    }
 
    int temp=nums[p];
    nums[p]=nums[q];
    nums[q]=temp;
 
    if(p<nums.length-1){
        nums = reverse(nums, p+1, nums.length-1);
    }
    return nums;
}
 
public int[] reverse(int[] nums, int left, int right){
    while(left<right){
        int temp = nums[left];
        nums[left]=nums[right];
        nums[right]=temp;
        left++;
        right--;
    }
    return nums;
}
```