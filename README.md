//C++ Program to Implement Min Heap
 
#include <iostream.h>

#include <conio.h>

using namespace std;

void min_heapify(int *b,int i,int n)
{
    int k, temp;
    temp = b[i];
    k = 2 * i;
    while (k <= n)
    {
        if (k < n && b[k+1] < b[k])
            k = k + 1;
        if (temp < b[k])
            break;
        else if (temp >= b[k])
        {
            b[k/2] = b[k];
            k = 2 * k;
        }
    }
    b[k/2] = temp;
    return;
}
void build_minheap(int *b, int n)
{
    int i;
    for(i = n/2; i >= 1; i--)
    {
        min_heapify(b,i,n);
    }
}
int main()
{
    int n, i, y;
    cout<<"enter no of elements of array\n";
    cin>>n;
    int b[20];
    for (i = 1; i <= n; i++)
    {
        cout<<"enter element"<<(i)<<endl;
        cin>>b[i];
    }
    build_minheap(b, n);
    cout<<"Min Heap\n";
    for (i = 1; i <= n; i++)
    {
        cout<<b[i]<<endl;
    }
    getch();
    return 0;
}



