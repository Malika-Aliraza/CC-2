## Product Of Array Except Self (Problem N.o 238)
class Solution {
    public int[] productExceptSelf(int[] nums) {
        int n=nums.length;
        int[] res = new int[n];
        int productOfAllBeforeCurrent = 1;
        int productOfAllAfterCurrent = 1;
        
        for(int i=0; i<n; i++){
            res[i] = productOfAllBeforeCurrent;
            productOfAllBeforeCurrent *= nums[i]; 
        }
        System.out.println(Arrays.toString(nums));
        System.out.println(Arrays.toString(res));

        for(int i=n-1; i>=0; i--){
            res[i] *= productOfAllAfterCurrent;
            productOfAllAfterCurrent *= nums[i];
        }
        return res;
    }
}
