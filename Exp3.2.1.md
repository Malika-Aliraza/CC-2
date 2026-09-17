## Coin Change (Problme N.o 322)

class Solution {
public:
    int myMin(const int& a, const int& b){
        if(a<b)
            return a;
        else
            return b;
    }
    int coinChange(vector<int>& coins, int amount) {
        if(amount==0)
            return 0;
        std::sort(coins.begin(),coins.end());
        std::vector<int>dp(amount+1,amount+1);
        dp[0]=0;
        for(int i=0;i<amount+1;i++)
        {
            for(const auto& c:coins)
            {
                if(c<=i)
                    dp[i]=myMin(dp[i],1+dp[i-c]);
            }
        }
        if(dp[amount]<amount+1)
            return dp[amount];
        else
            return -1;

        return{};
    }
};
