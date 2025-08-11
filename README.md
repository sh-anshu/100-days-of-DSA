1. two sum
class Solution {
    public int[] twoSum(int[] nums, int target) {
     Map<Integer, Integer> map = new HashMap<>();
        for(int i=0; i<nums.length;i++){
            int comp = target - nums[i];
            if(map.containsKey(comp))
                return new int[] { map.get(comp), i };
            map.put(nums[i],i);
        }
        return new int[] {};
    }
}
2. best time to sell or buy stock
class Solution {
    public int maxProfit(int[] prices) {
        int min = prices[0];
        int profit = 0;
        
        for(int i=0; i<prices.length; i++){
            if(prices[i] < min){
                min = prices[i];
            }
            
            profit = Math.max(profit, prices[i]-min);
        }
        
        return profit;
    }
}
3.Container With Most Water
class Solution {
    public int maxArea(int[] height) {
        int max = 0;
        int left = 0;
        int right = height.length -1;
        while(left<right) {
            int width = right-left;
            int area = Math.min(height[left], height[right])*width;
            max = Math.max(max, area);

            if(height[left]<=height[right]){
                left++;
            }
            else{
                right--;
            }
        }
        return max;
    }
}
4. rotate image
class Solution {
    public void rotate(int[][] matrix) {
        int n=matrix.length;

        for(int i=0;i<n;i++)
        {
            for(int j=i+1;j<n;j++)
            {
                int temp=matrix[i][j];
                matrix[i][j]=matrix[j][i];
                matrix[j][i]=temp;
            }
        }

        for(int i=0;i<n;i++)
        {
            for(int j=0;j<n/2;j++)
            {
                int temp=matrix[i][j];
                matrix[i][j]=matrix[i][n-j-1];
                matrix[i][n-j-1]=temp;
            }
        }
    }
}
5. reverse a string
class Solution {
    public void reverseString(char[] s) {
        int n = s.length;
        int left = 0;
        int right = n-1;
        while(left<right) {
            char temp = s[left];
            s[left] = s[right];
            s[right] = temp;
            left++;
            right--;
        }
    }
}
