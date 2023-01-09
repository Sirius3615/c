# C-jezik (zadaci)

1. Napiši program koji će računati potencije bez funkcije `pow`, unosi se baza `a` i eksponent `n`, te računa `p=a^n`

```c
#include <stdio.h>

main() {
	int a, n, p=1, i;
    
	printf("Unesi a: ");
	scanf("%d", &a);
	printf("Unesi n: ");
	scanf("%d", &n);
    
	for (i=1; i<=n; i++) {
		p = a * p;
	}
    
	printf("rezultat: %d ", p);
}
```

2. Napiši program koji će za uneseni prirodni broj `n` izračunati sumu. `S= 1+2^2...`

```c
#include <stdio.h>

main() {
	int j, n, p, i,s=0;
	printf("Unesi n: ");
	scanf("%d", &n);
	
	for (i=1; i<=n; i++){
		p = 1;
	for (j=1; j<=i; j++){
		p = p * i;
	}		 
	    s=s+p;
	}
    
	printf("rezultat: %d", s);
}
```

3. Napiši program koji će za uneseni prirodni broj `n` izračunavati zbroj faktorijela. `S= 1!+2!+3!...`

```c
#include <stdio.h>

main() {
	int s=0, i, n, f, j;
	printf("Unesi n: ");
	scanf("%d", &n);
    
	for (i=1; i<=n; i++) {
		f = f * i;
		s = s + f;
	}

	printf("rezultat: %d ", s);
}
```
4. Napiši program koji če za uneseni cijeli broj `x` i broj `n` računati sumu. `S=1+x+x^2/2!...`

```c
#include <stdio.h>

main() {
	int i, n;
	float r=1, e=1, x;
	
	printf("Unesi x: ");
	scanf("%f", &x);
	printf("Unesi n: ");
	scanf("%d", &n);
	
	for (i=1; i<=n; i++) {
		r = r *x/i;
		e = e + r;
	}
	
	printf("e = %.5f ", e);
}
```

5. Napiši program koji će unositi prirodni broj `n` te računati sumu. `S= 1+ 1+2/2!...`

```c
#include <stdio.h>

main() {
	int i, n;
	float s=0, bro=0, naz=1;
	
	printf("Unesi n: ");
	scanf("%d", &n);
	
	for (i=1; i<=n; i++) {
		bro = bro + i;
		naz = naz * i;
		s = s + bro/naz;
	}
	
	printf("s = %.2f ", s);
}
```

6. Napiši program koji računa zbroj znamenki učitanog prirodnog broja.

```c
#include <stdio.h>

main() {
	int n, z, s=0;
	
	printf("Unesi broj: ");
	scanf("%d", &n);
	
	while(n != 0) {
		z = n % 10;
		n = n / 10;
		s = s + z;
	}
	
	printf("%d ", s);	
}
```

7.  Napiši program koji će unositi cijele brojeve sve dok se ne unese 0, te ispisati koliko je uneseno pozitivnih, a koliko negativnih brojeva.

```c
#include <stdio.h>

main() {
	int b, p=0, n=0;
		printf("Unesi broj: ");
		scanf("%d", &b);

	while(b != 0) {
		if(b>0) p++; 
		else n++;
		printf("Unesi broj: ");
		scanf("%d", &b);	
	}
	printf("ima %d pozitivnih i %d negativnih brojeva", p, n);				
}
```

8. Napiši koji će učitavati prirodan broj `n`, te ispisati je li prost.

```c
#include <stdio.h>
main(){
	int n , i;
	printf ("Unesi broj: ");
	scanf ("%d",&n);
	
	for (i=2; i<=n/2; i++){
	
	if(n%i==0){
		printf("broj nije prost");
		goto A;
	}
}
	printf("broj je prost");
	A: return 0;
}
```
9. Napiši program koji unosi prirodni broj `n` te ispisuje prvi sljedeći nakon njega koji je prost.

```c
#include <stdio.h>
main(){
	int n , i, prost=0;
	printf ("Unesi broj: ");
	scanf ("%d",&n);
	while(prost==0){
	
	n++;
	for (i=2; i<=n/2; i++){
	
	if(n%i==0){
		printf("broj nije prost");
		goto A;
	}
}
	prost = 1;
	A: ;
	}
	printf("Prvi sljedeci prosti broj je: %d",n);
}
```
10. Napiši program koji unosi brojeve sve dok se ne unese `-1`. Program treba upisati koliko je brojeva među njima djeljivo s `5`.

```c
#include <stdio.h>
main(){
	int n , i, djeljiv=0;
	printf ("Unesi broj: ");
	scanf ("%d",&n);
	
	do {
	if(n%5==0) djeljiv++;
		
	printf ("Unesi broj: ");
	scanf ("%d",&n);
	
	} while (n != -1);
	
	printf("%d unesenih brojeva je djeljivo s 5", djeljiv);
}
```
11. Napiši program koji će unositi brojeve sve dok se ne unese broj koji je djeljiv s `3`. Program treba ispisati koliko je uneseno brojeva i njihov zbroj.

```c
#include <stdio.h>
main(){
	int n , brojeva=0, zbroj=0;
	printf ("Unesi broj: ");
	scanf ("%d",&n);
	
	do {
	brojeva++;
	zbroj = zbroj + n;
		
	printf ("Unesi broj: ");
	scanf ("%d",&n);
	} while (n%3 != 0);
	
	printf("uneseno je %d brojeva, i njihov zbroj je: %d", brojeva, zbroj);
}
```
12. Napiši program koji će ispitati je li uneseni prirodni broj potpuno neparan ili nije (broj je potpunoi neparan ako mu je svaka znamenka neparna).

```c
#include<stdio.h>
main() {
	int n,znam;
	printf("unesi neki broj:");
	scanf("%d",&n);
	while(n!=0){
		znam=n%10;
		n=n/10;
		if(znam%2==0){
			printf("broj nije potpuno neparan.");
			goto A;
		}
	}
	printf("broj je potpuno neparan.");
	A:return 0;
}
```

13. Napiši program koji unosi cijele brojeve sve dok se ne unese `0`, te ispisuje koliko ih ima točno jednu parnu znamenku.

```c
#include <stdio.h>
main(){
	int n, znam, a, parno=0, broj=0 ;
	
	do {
	printf ("Unesi broj: ");
	scanf ("%d",&n);
	a = n;
	
	while(a != 0){
	znam=a%10;
	a=a/10;
	
	if(znam%2 == 0) parno++;
	}  
	if(parno == 1) broj++;
	} while (n != 0);
	
	printf("%d unesenih brojeva ima tocno jednu parnu znamenku", broj);
	
}
```
14. Niz primjer: Napiši program koji će unositi `10` člani niz brojeva te isti ispisuje.

```c
#include <stdio.h>
main()
{
	int i,a[10];
	/* unos elemenata niza */
	for (i=0;i<10;i=i+1)
	{
		printf("a[%d]=",i);
		scanf("%d",&a[i]);
	}
	/* ispis elemenata niza */
	printf("\nElementi niza su: \n");
	for(i=0;i<10;i=i+1)
	{
		printf("%d ",a[i]);
	}
	return 0;
}
```
15.  Napiši program koji unosi broj učenika u razredu te nakon toga opće uspjehe. Program računa i ispisuje prosjek razreda (koristi nizove).

```c
#include <stdio.h>
main()
{
	int i,a[25], b, s=0;
	float p;
	/* unos elemenata niza */
	printf("Unesi broj ucenika: ");
	scanf("%d",&b);
		
	for (i=0;i<b;i=i+1)
	{
		printf("a[%d]=",i);
		scanf("%d",&a[i]);
		s=s+a[i]; // zbroj ocijena
	}
	
	p=s/b;
	printf("Prosijek ocijena je: %.2f", p);
	return 0;
}
```
16. Napiši program koji će unositi broj učenika u razredu te ocjene za svakog, te na kraju ispisati koliko je ispodprosječnih učenika.

```c
#include <stdio.h>
main()
{
	int i,a[25], b, s=0, c=0;
	float p;
	/* unos elemenata niza */
	printf("Unesi broj ucenika: ");
	scanf("%d",&b);
		
	for (i=0;i<b;i=i+1)
	{
		printf("a[%d]=",i);
		scanf("%d",&a[i]);
		s=s+a[i]; // zbroj ocijena
	}
	p=s/b; // prosjek
	
	for (i=0; i<b; i++) {
		if(a[i] < p) c++;
	}
	printf("Prosijek ocijena je: %.2f, a ima %d ispod prosijecnih ucenika", p, c);
	return 0;
}
```
17. Napiši program koji će unositi 10 članmi niz brojeva, te ispisati najmanji među njima.

```c
#include <stdio.h>
main()
{
	int i,a[10], min;
	/* unos elemenata niza */
	for (i=0;i<10;i=i+1)
	{
		printf("a[%d]=",i);
		scanf("%d",&a[i]);
	}
	min=a[1];
	for(i=0;i<10;i++) {
		if(min > a[i]){
			min=a[i];
		}
	}
	printf("Najmanji broj je: %d", min);
	return 0;
}
```

18. Napiši program koji će unositi 10 članmi niz brojeva, te ga ispisuje sortiranog od manjeg prema većem.

```c
#include <stdio.h>
main()
{
	int i, j, a[10], p;
	/* unos elemenata niza */
	for (i=0;i<10;i=i+1)
	{
		printf("a[%d]=",i);
		scanf("%d",&a[i]);
	}
	/* ispis elemenata niza */
	
	for (i=0; i<10; i++) {
		for(j=i+1; j<10; j++) {
			if(a[j] < a[i]) {
				// zamjena a[i] i a[j]
				p = a[i];
				a[i] = a[j];
				a[j] = p;
			} 
		}
	}
	
	printf("\nElementi niza su: \n");
	for(i=0;i<10;i=i+1)
	{
		printf("%d ",a[i]);
	}
	return 0;
}
```

19. Napiši program koji unosi cijeli dekatski broj (do 10 znamenki) te ga pretvara u binarni.

```c
#include <stdio.h>
main()
{
	int i=0, j, n, p, a[100];
		
	printf("unesi broj do 10 znamenki");
	scanf("%d",&n);

	// pretvorba u binarni
	while(n>0) {
		a[i]=n%2;    
		n=n/2;
		i++;
	}
		
	/* ispis elemenata niza */
	printf("\nBinarni broj je: \n");
	for(j=i-1;j>=0;j--)
	{
		printf("%d",a[j]);
	}
	
	return 0;
}
```
20. LOTO 7/39
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

main() {
	int x, i, a[7], j, p;
	
	printf("LOTO 7/39 \n\n");
	srand(time(NULL));
	for(i=0; i<7; i++) {
	A:	x = rand() % 39 + 1;
		for (j=0; j<i-1; j++) {
			if(x == a[j]) goto A;			
		}
		a[i] = x;
		printf("%d. izvuceni broj je: %d \n",i+1,a[i]);
	}
	
	// sortiranje i ispis
	for (i=0; i<6; i++) {
		for(j=i+1; j<7; j++) {
			if(a[j] < a[i]) {
				p = a[i];
				a[i] = a[j];
				a[j] = p;
			} 
		}
	}

	//ispis
	printf("\nDobitna kombinacija je: \n");
	for(i=0;i<7;i++)
	{
		printf("%d ",a[i]);
	}
	return 0;
}
```

21. Duljina riječi (char)
```c
#include <stdio.h>

main() {
	char a[20];
	int i=0;
	
	printf("Unesi rijec: ");
	gets(a);

	while(a[i+1] != '\0') {
		i++;	
	}
	printf("duljina rijeci je %d", i);
}
```

22. Duljina riječi sa `strlen()` 
```c
#include <stdio.h>
#include <string.h>

main() {
	char a[20];
	int i=0;
	
	printf("Unesi rijec: ");
	gets(a);

	i = strlen(a);
	
	printf("duljina rijeci je: %d", i);
}
```

23. Obrnuta riječ
```c
#include <stdio.h>
#include <string.h>

main() {
	char a[20];
	int i=0, j;
	
	printf("Unesi rijec: ");
	gets(a);
	i = strlen(a);
	
	for (j=i-1; j>=0; j--) {
		printf("%c", a[j]);
	}	
}
```

---

