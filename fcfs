#include<stdio.h>
struct pro
{
	int num;
	int at;
	int bt;
};
void sort(struct pro p[],int n)
{
	for(int i=0;i<n;i++)
	{
		for(int j=0;j<n-1-i;j++)
		{
			if(p[j].at>p[j+1].at)
			{
				struct pro temp=p[j];
				p[j]=p[j+1];
				p[j+1]=temp;
			}
			else if(p[j].at==p[j+1].at)
			{
				if(p[j].num>p[j+1].num)
				{
					struct pro temp=p[j];
					p[j]=p[j+1];
					p[j+1]=temp;
				}
			}
		}
	}
}

void main()
{
	int n,sum=0;
	printf("Enter number of processes:");
	scanf("%d",&n);
	struct pro p[n];
	printf("Enter process number,Arrival time,Burst time:");
	for(int i=0;i<n;i++)
	{
		scanf("%d %d %d",&p[i].num,&p[i].at,&p[i].bt);
	}
	sort(p,n);
	
	sum=sum+p[0].at;
	int ct[40],tat[40],wt[40];
	//ct[0]=sum;
	for(int i=0;i<n;i++)
	{
		sum=sum+p[i].bt;
		ct[i]=sum;
	}
	printf("CT time:");
	for(int i=0;i<n;i++)
	{
		printf("%d\t",ct[i]);
	}
	
	for(int i=0;i<n;i++)
	{
		tat[i]=ct[i]-p[i].at;
	}
	int stat=0;
	printf("\nTAT time:");
	for(int i=0;i<n;i++)
	{	
		stat+=tat[i];
		printf("%d\t",tat[i]);
	}
	int swt=0;
	for(int i=0;i<n;i++)
	{
		wt[i]=tat[i]-p[i].bt;
	}
	printf("\nWT time:");
	for(int i=0;i<n;i++)
	{
		swt+=wt[i];
		printf("%d\t",wt[i]);
	}
	printf("\n ATAT:%f",((float)stat/n));
	printf("\n AWT:%f",((float)swt/n));
}
