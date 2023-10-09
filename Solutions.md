## Completed Problems

LeetCode # | Title 
----------------|-------
1 | Two Sum
21 | Merge Two Sorted Lists
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

### Merge Two Sorted Lists

    /**
     * Definition for singly-linked list.
     * struct ListNode {
     *     int val;
     *     struct ListNode *next;
     * };
     */
    
    struct ListNode* mergeTwoLists(struct ListNode* l1, struct ListNode* l2)
    {
        struct ListNode head;
        struct ListNode *h = &head;
        
        if (l1 == NULL && l2 == NULL)
            return NULL;
        
        while (l1 && l2) {
            if (l1->val < l2->val) {
                h->next = l1;
                l1 = l1->next;
                h = h->next;
            } else {
                h->next = l2;
                l2 = l2->next;
                h = h->next;
            }
        }
    
        if (l1) {
            h->next = l1;
        }
        if (l2) {
            h->next = l2;
        }
      
        return head.next;
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
