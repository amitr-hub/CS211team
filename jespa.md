

# Profile: Jd Esparza

- **NetID:** 652829238
- **Major:** CS and Linguistics
- **Question that I chose from the memoization exercise:** Maximum Subarray Sum
- **Link to the question article:** https://www.geeksforgeeks.org/dsa/largest-sum-contiguous-subarray/ 
- **My solution:**

```cpp
class Solution {
public:
    int maxSubarraySum(vector<int>& arr) {
        // have to initialize variables and keep track 
        // of current place and the largest value
        // need to loop through entirely 
        // compare values and assign the larger one


        int largestVal = arr[0];
        int currVal = arr[0];

        for (int i = 1; i < arr.size(); i++) {
            // Checks if arr[i] is larger than sum of currVal and arr[i] and assigns the higher value
            
            if (arr[i] > currVal + arr[i]) {
                currVal = arr[i];
            } else {
                currVal = currVal + arr[i];
            }
            
            // Checks if currVal beats largestVal, and assigns it if it is greater
            if (currVal > largestVal) {
                largestVal = currVal;
            }
        }
        
        return largestVal;
    }
};
