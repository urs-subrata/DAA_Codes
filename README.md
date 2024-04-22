#include <stdio.h>
int p[10];
int mcm(int i, int j)
{
    int min = 99999, k, r;
    if (i == j)
    {
        return 0;
    }
    else
    {
        for (k = i; k < j; k++)
        {
            r = mcm(i, k) + mcm(k + 1, j) + (p[i - 1] * p[k] * p[j]);
            if (r < min)
            {
                min = r;
            }
        }
        return min;
    }
}
int main()
{
    int i, j, r, n;
    printf("Enter the no. of matrix:");
    scanf("%d", &n);
    printf("enter the orders:");
    for (i = 0; i <= n; i++)
    {
        scanf("%d", &p[i]);
    }
    i = 1;
    j = n;
    r = mcm(i, j);
    printf("result is %d", r);
    return 0;
}
