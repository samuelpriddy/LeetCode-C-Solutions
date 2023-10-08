## Completed Problems

LeetCode # | Title 
----------------|-------
1 | Two Sum
28 | Find the Index of the First Occurrence in a String

## Implementations

### Two Sum
    /**
     * Note: The returned array must be malloced, assume caller calls free().
     */
    int* twoSum(int* nums, int numsSize, int target, int* returnSize){
        int* returnArray = malloc(sizeof(int) * 2);
        returnArray[0] = -1;
        returnArray[1] = -1;
    
        for(int i=0; i<numsSize; i++){
            for(int j=i+1; j<numsSize; j++){
                if(nums[i] + nums[j] == target){
                    returnArray[0] = i;
                    returnArray[1] = j;
                    *returnSize = 2;
                    return returnArray;
                }
            }
        }
        return returnArray;
    }

### Find the Index of the First Occurrence in a String

    int strStr(char * haystack, char * needle){
        int haystack_len = strlen(haystack);
        int needle_len = strlen(needle);
    
        if (needle_len > haystack_len)
                return -1;
    
        for(int i=0; i<haystack_len-needle_len+1; i++){
            if(strncmp(haystack+i, needle, needle_len) == 0)
                return i;
        }
        return -1;
    }
