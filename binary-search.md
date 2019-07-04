# Binary search

## Template
```python
def binarySearch(nums, target):
    """
    :type nums: List[int]
    :type target: int
    :rtype: int
    """
    if len(nums) == 0:
        return -1

	left, right = 0, len(nums)
	# why '<' ? rather than '<=' ?
    # 1. l = 1, r = 2
    # 2. mid = (1 + 2) // 2 = 1
    # 3. nums[2] < target
    # 4. l := 1 + 1 = 2
    # 5. If in While statement operator is '<=', this loop will not end here
    # 6. l = 2, r = 2
    # 2. mid = (2 + 2) // 2 = 2
    # 3. nums[2] = 
	while left < right:
    	mid = (left + right) // 2
    	if nums[mid] == target:
        	return mid
    	elif nums[mid] < target:
    		# why +1 ?
    		# 1. l = 0, r = 1
    		# 2. mid = (0 + 1) // 2 = 0
            # 3. nums[0] < target
            # 4. l := 0
            # Repeat step 1.
            # If mid don't plus 1, it will casuse endless loop.
        	left = mid + 1
    	else:
        	right = mid

	# Post-processing:
	# End Condition: left == right
	if left != len(nums) and nums[left] == target:
    	return left
	return -1
```

