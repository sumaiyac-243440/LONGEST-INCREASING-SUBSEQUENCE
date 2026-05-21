#include <iostream>
using namespace std;

int main()
{
    int arr[] = {10, 22, 9, 33, 21, 50};

    int n = 6;

    int dp[100];

    // initialize
    for(int i = 0; i < n; i++)
    {
        dp[i] = 1;
    }

    // LIS calculation
    for(int i = 1; i < n; i++)
    {
        for(int j = 0; j < i; j++)
        {
            if(arr[i] > arr[j])
            {
                dp[i] = max(dp[i], dp[j] + 1);
            }
        }
    }

    int ans = 0;

    for(int i = 0; i < n; i++)
    {
        ans = max(ans, dp[i]);
    }

    cout << "Length of LIS = " << ans;

    return 0;
}
