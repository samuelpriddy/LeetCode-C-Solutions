## Completed Problems

LeetCode # | Title 
----------------|-------
28 | Find the Index of the First Occurrence in a String

## Implementations

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
