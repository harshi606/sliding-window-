# sliding-window-

This is one of the most important and favorite algortihms that finds its application is many interviews. 

My learning of this algorithm was a real fun as I learnt very deep.

Thanks to Adithya Verma Bhaiya for the most wonderful tutorials on this algorithm and the whole of dp.

https://youtube.com/playlist?list=PL_z_8CaSLPWeM8BDJmIYDaoQ5zuwyxnfj

This is the link for that insightful tutorial. Kindly watch it if you want to gain in-depth knowledge !!

I will be pushing some common problems related to sliding window so that we can cluster it seperately and can refer it at the time of interviews !(I am currently prep for interview :) I will be using this for my revision !) I thought to make this public so that many people out there can also use this.

I will try my best to update all possible questions

1. Given an array of integers Arr of size N and a number K. Return the maximum sum of a subarray of size K.(GFG,Basic)


question: https://practice.geeksforgeeks.org/problems/max-sum-subarray-of-size-k5313/1


solution: https://ide.geeksforgeeks.org/wHhwysn3EV

2.Given a word pat and a text txt. Return the count of the occurences of anagrams of the word in the text.

question: https://practice.geeksforgeeks.org/problems/count-occurences-of-anagrams5839/1


solution:
#include <bits/stdc++.h>

using namespace std;


 // } Driver Code Ends
//User function template for C++
class Solution{
public:
	int search(string pat, string txt) {
	    // code here
	   unordered_map <char, int> count;
	   
	    int counter;
	    int i=0;
	    int j=0;
	    int k = pat.size();
	    for(auto it:pat){
	        count[it]++;
	    }
	    
	    counter = count.size();
      int result=0;
	    
	    while( j < txt.size()){
	        if(count.find(txt[j]) != count.end()){
	            count[txt[j]]--;
	
	        if(count[txt[j]] == 0)
	            counter--;
	        }
	        
	        if(j-i+1 < k)
	            j++;
	        
	       else if(j-i+1 == k){
	            if(counter == 0)
	                result++;
	            
	       if(count.find(txt[i]) != count.end()){
	           count[txt[i]]++;
	       
	       if(count[txt[i]] == 1)
	           counter++;
	       }
	       
	       i++;
	       j++;
	       
	        }
	    }
	    
	    return result;
	}

};

// { Driver Code Starts.

int main() {
    int t;
    cin >> t;
    while (t--) {
        string pat, txt;
        cin >> txt >> pat;
        Solution ob;
        auto ans = ob.search(pat, txt);
        cout << ans << "\n";
    }
    return 0;
}  // } Driver Code Ends
