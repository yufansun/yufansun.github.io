---
layout: post
title:  "Programming tricks"
date:   2016-09-15 23:33:17 -0400
categories: Programming questions
author: Yufan Sun
---
# Image rotation

  * clockwise rotate
  first reverse up to down, then swap the symmetry 

    1 2 3     7 8 9     7 4 1

    4 5 6  => 4 5 6  => 8 5 2

    7 8 9     1 2 3     9 6 3
  {%highlight c++ %}
  void rotate(vector<vector<int> > &matrix) {
    reverse(matrix.begin(), matrix.end());
    for (int i = 0; i < matrix.size(); ++i) {
        for (int j = i + 1; j < matrix[i].size(); ++j)
            swap(matrix[i][j], matrix[j][i]);
    }
}
{% endhighlight %}
  * counterclockwise rotage
  first reverse left to right, then swap the symmetry

    1 2 3     3 2 1     3 6 9

    4 5 6  => 6 5 4  => 2 5 8

    7 8 9     9 8 7     1 4 7

# Template that can solve most 'substring' problems

* For most substring problem, we are given a string and need to find a substring of it which satisfy some restrictions. A general way is to use a hashmap assisted with two pointers. The template is given below.
*   {%highlight c++ %}
int findSubstring(string s){
vector<int> map(128,0);
int counter; // check whether the substring is valid
int begin=0, end=0; //two pointers, one point to tail and one  head
int d; //the length of substring

for() { /* initialize the hash map here */ }

while(end<s.size()){

    if(map[s[end++]]-- ?){  /* modify counter here */ }

    while(/* counter condition */){ 

        /* update d here if finding minimum*/

        //increase begin to make it invalid/valid again

        if(map[s[begin++]]++ ?){ /*modify counter here*/ }
    }  

    /* update d here if finding maximum*/
    }
    return d;
}
{% endhighlight %}

# Permutation related question

## Recursive solution
Basic idea: permutation of A[1..n] equals to
A[1] + permutation of (A[1..n] - A[1])
A[2] + permutation of (A[1..n] - A[2])
...
A[n] + permutation of (A[1..n] - A[n]).

## Use code in nextPermutation
Next permutation:
1. Find the largest index k such that nums[k] < nums[k + 1]. If no such index exists, the permutation is sorted in descending order, just reverse it to ascending order and we are done. For example, the next permutation of [3, 2, 1] is [1, 2, 3].
2. Find the largest index l greater than k such that nums[k] < nums[l].
3. Swap the value of nums[k] with that of nums[l].
4. Reverse the sequence from nums[k + 1] up to and including the final element nums[nums.size() - 1].

*   {%highlight c++ %}
class Solution {
public:
    void nextPermutation(vector<int>& nums) {
        int k=-1,i;
        for (i=nums.size()-1;i>0;i--) {
            if(nums[i]>nums[i-1]) {
                k=i-1;
                break;
            }
        }
        if (k==-1) {
            reverse(nums.begin(),nums.end());
            return;
        } else {
            int j,l=-1;
            for (j=nums.size()-1;j>k;j--) {
                if(nums[j]>nums[k]) {
                    l=j;
                    break;
                }
        }
        swap(nums[k],nums[j]);
        reverse(nums.begin()+k+1,nums.end());
        }
    }
};
{% endhighlight %}

