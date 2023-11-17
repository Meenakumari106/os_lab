#include<stdio.h>
struct pro
{
	int num;
	int at;
	int bt;
	int ct;
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
void sjf(struct pro p[],int n)
{
	int visit[20];
	for(int i=0;i<n;i++)
	{
		visit[i]=0;
	}
	int len=n;
	int temp=0;
	int min,ind;
	visit[0]=1;
	temp=p[0].at+p[0].bt;
	p[0].ct=temp;
	while(len>1)
	{
		min=999;ind=-1;
		for(int i=0;i<n;i++)
		{
			if(visit[i]!=1 && p[i].at<=temp)
			{
				if(min>p[i].bt)
				{
					min=p[i].bt;
					ind=i;
				}
			}
			
		}
		//printf("%d",min);
		
		temp+=p[ind].bt;
		p[ind].ct=temp;
		visit[ind]=1;
		len=len-1;
	}
	for(int i=0;i<n;i++)
	{
		printf("%d\t",p[i].ct);
		
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
	sjf(p,n);
	
}
