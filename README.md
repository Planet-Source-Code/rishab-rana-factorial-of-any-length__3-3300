<div align="center">

## Factorial of any length


</div>

### Description

Finds the factorial of large numbers.
 
### More Info
 
the program find out using simple multiplication the way we do on a paper.

1) find the length of the number so that we can have that big buffer

log10 of any number + 1 gives u the length of the number

2) just multplies like we do on paper


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Rishab Rana](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/rishab-rana.md)
**Level**          |Beginner
**User Rating**    |5.0 (15 globes from 3 users)
**Compatibility**  |C, C\+\+ \(general\), Microsoft Visual C\+\+
**Category**       |[Algorithms](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/algorithms__3-29.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/rishab-rana-factorial-of-any-length__3-3300/archive/master.zip)





### Source Code

```
#include <math.h>
#include <malloc.h>
#include <iostream.h>
#include <process.h>
void main()
{
	unsigned int d;	//number of digits
	unsigned char *a;
	unsigned int j, n, q, z, t;
	int i;
	double p;
	cout << "\nEnter the No\t:";
	cin >> n;
	p = 0.0; //calculate the number of digits required
	for(j = 2; j <= n; j++)
		p += log10(j);
	d = (int)p + 1;
	a = (unsigned char*)malloc(d*sizeof(unsigned char));
	if (!a)
	{
		cout << "Could not allocate memory!!!";
		exit(0);
	}
	for (i = 1; i < d; i++)
		a[i] = 0; //initialize
	a[0] = 1;
	p = 0.0;
	for (j = 2; j <= n; j++)
	{
		q = 0;	//initialize remainder to be 0
		p += log10(j);
		z = (int)p + 1;
		for (i = 0; i <= z/*NUMDIGITS*/; i++)
		{
			t = (a[i] * j) + q;
			q = (t / 10);
			a[i] = (char)(t % 10);
		}
	}
	cout << "\nThe Factorial is\n";
	// the fact is stored ulta..
	for( i = d -1; i >= 0; i--)
	{
		cout << (int)a[i];
	}
}
```

