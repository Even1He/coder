//水仙花数进阶，求任意n位数的水仙花数//

```
#include <stdio.h>
#include <math.h>
int main()
{
	int n,i;
	int sum;
	int count=0;
	scanf_s("%d", &n);
	int low = pow(10, n-1);
	int high = pow(10,n) - 1;

	for (i = low; i <= high; ++i) 
	{
		int t = i;
		int m = n; 
		sum = 0;
		for (int j = 1;; j++) 
		{
			m--;
			int x = t / pow(10, m);
			int y = t % (int)pow(10, m);
			sum += pow(x, n);
			t = y;
			if (y == 0) 
			{
				break;
			}
		}
		if (sum == i) 
		{
			count++;
			printf("%d ", i);
		}
	}
	putchar('\n');
	printf("位数为 %d 的数的水仙花数有 %d 个\n", n,count);
	return 0;
}
```
