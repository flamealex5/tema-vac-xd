# tema by xXx_fl@m3@l3x_xXx a.K.a codi


//1.Scrieti un program care citeste de la tastatura un numar natural si verifica daca este prim.

#include <iostream>

using namespace std;

int main()
{
    int n,prim=1,d=2;
    cout << "n="; cin >> n;

    while(d<=n/2)
    {
        if(n%d==0)
        prim=0;
        d++;
    }
    if(prim==1)
        cout << "Da";
    else
        cout << "Nu";
    return 0;
}

//2. Scrieti un program care citeste de la tastatura un numar natural si scrie pe ecran toti divizorii sai.
#include <iostream>

using namespace std;

int main()
{
    int n,x=1;
    cout << "n="; cin >> n;

    while(n!=x-1)
    {
        if(n%x==0)
            cout << x << " ";
        x++;
    }
    return 0;
}

//3. Scrieti un program care citeste de la tastatura un numar natural si scrie pe ecran toti divizorii sai primi.
#include <iostream>

using namespace std;

int main()
{
    int n,d=2,x;
    cout << "n="; cin >> n;

    while(d<=n/2)
    {
        if(n%d==0)
            cout << d << " ";
        d++;
    }
    return 0;
}

//4. Scrieti un program care citeste de la tastatura un numar natural si scrie pe ecran descompunerea sa in factori primi.
//Exemple: daca citeste 60, va afisa: 60 = 2^2 * 3 * 5; daca citeste 8, va afisa: 8 = 2^3; daca citeste 5, va afisa: 5 = 5;daca citeste 1, va afisa: 1 = 1; daca citeste 0, va afisa: 0 = 0
#include <iostream>

using namespace std;

int main()
{
    int n,d=2,p;
    cout << "n="; cin >> n;

    while(n>1)
    {
        p=0;
        while(n%d==0)
        {
            p++;
            n/=d;
        }
        if(p>0)
            cout << d << "^" << p << " ";
        d+=1;
    }
    return 0;
}

//5.Scrieti un program care citeste de la tastatura un numar natural si verifica daca este perfect (i.e. este egal cu suma divizorilor sai, printre divizori considerandu-se si 1,
//dar excluzandu-se numarul insusi). Se poate folosi si urmatoarea formula de calcul:
//n perfect <=> n = 2p-1 * (2p - 1), unde p si 2p - 1 sunt prime. Exemple de numere perfecte: 6, 28, 496, 8128.
#include <iostream>

using namespace std;

int main()
{
    int n,d,S=1;
    cout << "n="; cin >> n;
    for(d=2; d<=n/2; d++)
        if(n%d==0)
            S+=d;
    if(n==S)
        cout << "perfect";
    else
        cout << "nu";
    return 0;
}

//6.Scrieti un program care citeste de la tastatura 2 numere naturale si verifica daca sunt prietene
//(i.e. fiecare este suma divizorilor celuilalt, printre divizorii unui numar considerand si pe 1, dar excluzand numarul insusi).
//Exemple de numere prietene: 220 si 284, 17296 si 18416.
#include <iostream>

using namespace std;

int main()
{
    int a,Sa=1,b,Sb=1,d;
    cout << "a="; cin >> a;
    cout << "b="; cin >> b;

    for(d=2; d<=a/2; d++)
        if(a%d==0)
            Sa+=d;

    if(Sa==b)
    {
        for(d=2; d<=b/2; d++)
            if(b%d==0)
                Sb+=d;

        if(Sb==a)
            cout << "Prietenie";
        else
            cout << "Dusmani";
    }
    return 0;
}

//7. Scrieti un program care citeste de la tastatura un numar natural si calculeaza suma cifrelor sale.
#include <iostream>

using namespace std;

int main()
{
    int n,c,S=0;
    cout << "n="; cin >> n;

    while(n!=0)
    {
        c=n%10;
        S+=c;
        n=n/10;
    }
    cout << S;
    return 0;
}

//8. Scrieti un program care citeste de la tastatura un numar natural si determina daca este "special" (sau "deosebit") (
//un numar k este special daca nu exista nici un n natural astfel incat k = n +
//suma cifrelor lui n). Modificati apoi programul astfel incat sa se citeasca de la
//tastatura un numar natural n si sa se afiseze pe ecran toate numerele speciale din intervalul 1, ..., n.
#include <iostream>

using namespace std;

int main()
{
    int k,c,n,Sn,aux,x=0;
    cout << "k="; cin >> k;

    for(n=1; n<=k; n++)
    {
        aux=n;
        while(n!=0)
        {
            c=n%10;
            Sn+=c;
            n=n/10;
        }
        if(k!=aux+Sn)
            x++;
        n=aux;
    }
    if(x==k)
        cout << "Special";
    else
        cout << "blyat";
    return 0;
}

//9.Scrieti un program care citeste de la tastatura un numar natural si calculeaza
//suma cifrelor sale de pe pozitii pare (pozitiile se vor numara incepand de la cifra
//unitatilor). Exemple: pentru n = 12345, suma este 6 (= 4 + 2); pentru n = 123456, suma este 9 (= 5 + 3 + 1).
#include <iostream>

using namespace std;

int main()
{
    int n,k=0,c,Sc=0,aux;
    cout << "n="; cin >> n;

    while(n!=0)
    {
        c=n%10;
        n=n/10;
        k++;
        aux=c;
        if(k%2==0)
        {
            Sc+=c;
        }
    }

    cout << Sc;
    return 0;
}

//10.Scrieti un program care citeste de la tastatura un numar natural si calculeaza suma cifrelor sale pare.
#include <iostream>

using namespace std;

int main()
{
    int n,c,S=0;
    cout << "n="; cin >> n;

    while(n!=0)
    {
        c=n%10;
        n/=10;
        if(c%2==0)
            S+=c;
    }

    cout << S;
    return 0;
}

//12.Scrieti un program care citeste de la tastatura un numar natural
//si verifica daca este palindrom (i.e. daca citit si normal si invers este la fel).
//Exemple: 1, 11, 212, 42324 sunt numere palindrom, iar 12, 123, 42354 nu sunt numere palindrom.
#include <iostream>

using namespace std;

int main()
{
    int n,aux,x=0;
    cout << "n="; cin >> n;

    aux=n;
    while(n!=0)
    {
        x=x*10+n%10;
        n/=10;
    }

    if(x==aux)
        cout << "Da";
    else
        cout << "blyat";
    return 0;
}

//13.Scrieti un program care citeste de la tastatura un numar natural n si calculeaza
//1! + 2! + ... + n!. Pentru a se putea lucra si cu numere mai mari, se va folosi "longint".
#include <iostream>

using namespace std;

int main()
{
    long int n,i,P=1;
    cout << "n="; cin >> n;

    for(i=2; i<=n; i++)
        P*=i;

    cout << P;
    return 0;
}

//14.Scrieti un program care citeste de la tastatura un numar natural n si calculeaza: 11 + 22 + ... + nn .
#include <iostream>

using namespace std;

int main()
{
    long int n,i,S=0;
    cout << "n="; cin >> n;

    for(i=1; i<=n; i++)
        S=S+i+i*10;

    cout << S;
    return 0;
}

/*15.Scrieti un program care citeste de la tastatura 2 numere naturale, n si k
, unde k este de la 0 la 9, si verifica daca k apartine, ca cifra, lui n. Exemplu:
daca n=25145 si k=7, raspunsul este NU, daca n=25145 si k=5, raspunsul este DA.*/
#include <iostream>

using namespace std;

int main()
{
    int n,k,c,x=0;
    cout << "n="; cin >> n;
    cout << "k="; cin >> k;

    while(n!=0)
    {
        c=n%10;
        n/=10;
        if(c==k)
            x=1;
        else
            x=0;
    }
    if(x==1)
        cout << "DA";
    else
        cout << "blyat";
    return 0;
}

/*16.	De la tastatura se citesc doua numere naturale a si b (b>=2) si se scrie pe ecran r
eprezentarea lui a in baza b. Cifrele in baza b vor fi numerele
 0, ... , b-1, scrise in baza 10 si puse intre paranteze daca b>=11. Exemplu: daca
  b=7 si a=25, se va afisa: 34; daca b=12 si a=25, se va afisa: (2)(1); daca b=12 si a=135, se va afisa: (11)(3)*/
#include <iostream>

using namespace std;

int main()
{
    int a,b,nr=0,r,p=1;
	cout << "a="; cin >> a;
	cout << "b="; cin >> b;
	while(n!=0)
        {
		r=a%10;
		a/=10;
		nr=nr+r*p;
		p*=b;
        }
	cout << nr;
    return 0;
}

/*17.Scrieti un program care citeste de la tastatura un numar natural n si afisaza pe ecran toate tripletele de numere pitagoreice mai mici sau e
gale cu n (adica triplete de numere naturale i j k astfel incat
i*i + j*j = k*k si i,j,k<=n), fara repetitii modulo ordinea
(de ex., daca s-a afisat 3 4 5, nu se va afisa si 4 3 5). Numarul de calcule efectuate trebuie sa fie cat mai mic.*/
#include <iostream>
#include <stdlib.h>
#include <math.h>

using namespace std;

int main()
{
    int i,j,k,n;
    if(abs(pow(i,2))+abs(pow(j,2))==abs(pow(k,2)))
        cout << "i, j si k sunt numere pitagorice";
    else
        cout << "blyat";
    return 0;
}

/*18.Scrieti un program pentru calculul cmmdc al doua numere naturale citite de la tastatura
 folosind algoritmul lui Euclid prin impartiri. Aceeasi cerinta, dar folosind algoritmul lui
Euclid prin diferente.*/


#include <iostream>

using namespace std;

int main()
{
    cin >> a;
    cin >> b;

    while(a != b)
    {
        if(a > b)
            a = a - b;
        if(b > a)
            b = b - a;
    }

    cout << a;
    return 0;
}
//google.com/algoritm-euclid...

//19.Scrieti un program pentru rezolvarea ecuatiei de grad <=2 cu coeficienti reali
#include <iostream>
#include <cmath>

using namespace std;

int main()
{
    float a,b,c,x,delta,x1,x2;
    cout << "a="; cin >> a;
    cout << "b="; cin >> b;
    cout << "c="; cin >> c;

     if(a==0)
        if(b==0)
            if(c==0)
                cout << "Exista o infinitate de solutii!";
            else
                cout << "Ecuatie imposibila!";
            else
            {
            cout << "Ecuatie de gr I cu solutia ";
            x=-c/b;
            cout << x;
            }
            else

        {
        delta=pow(b,2)-4*a*c;
        if(delta<0)
            cout << "Ecuatia nu are solutii reale!";
        else if(delta==0)
                {
                cout << "Ecuatia are solutii egale!";
                cout << "x1=x2=" << -b/(2*a);
                }
            else
                {
                x1=(-b+sqrt(delta))/2*a;
                x2=(-b-sqrt(delta))/2*a;
                cout<<"Ecuatia are solutii reale!"<<endl;
                cout<<"x1="<<x1<<endl;
                cout<<"x2="<<x2 <<endl;
                }

        }
    return 0;
}

/*20.Scrieti un program care citeste de la tastatura
un numar natural n si sa afiseze al n-lea termen al sirului lui Fibonacci.*/
#include <iostream>

using namespace std;

int main()
{
    int n;
    cout << "n="; cin >> n;

    long long int  nr2,nr1,nr0;
    nr0 = 1;
    nr1 = 1;

    for(int i=3; i<=n; i++)
    {
        nr2=nr1+nr0;
        nr0=nr1;
        nr1=nr2;

        if(i==n)
            cout << nr2;
    }
    return 0;
}

//21.De la tastatura se citesc 3 numere reale, apoi se afiseaza aceste numere pe ecran in ordine crescatoare.
#include <iostream>

using namespace std;

int main()
{
    int a,b,c,aux;
    cout << "a="; cin >> a;
    cout << "b="; cin >> b;
    cout << "c="; cin >> c;

    if(a>b)
    {
        aux=a;
        a=b;
        b=aux;
    }
    if(b>c)
    {
        aux=b;
        b=c;
        c=aux;
    }
    if(c>a)
    {
        aux=c;
        c=a;
        a=aux;
    }

    cout << c << " " << b << " " << a;
    return 0;
}
