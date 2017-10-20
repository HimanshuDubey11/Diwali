# Diwali
#include<iostream>
#include<conio.h>
#include<stdlib.h>
#include<stdio.h>
#include<graphics.h>
#include<windows.h>
#include<dos.h>
#include<time.h>
using namespace std;


void rocket(int &r,int &c)
{
	setcolor(14);
			arc(683,768,0,10+5*r,700-c);
}
void eraserocket(int &r,int &c)
{		
	setcolor(0);
			arc(683,768,0,10+5*(r-4),700-c);
}
void glitter(int &r)
{
	setcolor(4);
	arc(703,384,83,90+8*(r-14),308);
	setcolor(1);
	arc(703,284,70-8*(r-14),80,208);
	setcolor(2);
	arc(503,184,22,28+5*(r-14),270);
}
void eraseglitter(int &r)
{
	setcolor(0);
	arc(703,384,83,90+8*(r-16),308);
	arc(703,284,70-8*(r-16),80,208);
	arc(503,184,22,28+5*(r-16),270);
}
int main()
{
	initwindow(1366,768);
	srand(time(NULL));
	int r=0,c=0;
	do
	{
		cleardevice();
		for(int i=0;i<1000;i++)
		{
			putpixel(rand()%1366+1,rand()%768+1,rand()%16+1);
			
		
		}
			if(r<16)
			rocket(r,c);
			
			
			if(r>=16 && r<21)
			{
				setcolor(14);
				arc(683,768,0,85,700-c);
			}
			if(r>4 && r<21)
			eraserocket(r,c);
			
			if(r>14 && r<23)
			glitter(r);
			
			if(r>16 && r<23)
			eraseglitter(r);
			settextstyle(1,0,5);
			setcolor(rand()%16+1);
			outtextxy(500,300,"Happy Diwali");
			settextstyle(1,0,4);
			setcolor(rand()%16+1);
			outtextxy(550,400,"To You All");
			settextstyle(1,0,3);
			setcolor(rand()%16+1);
			outtextxy(510,500," ~ BY XPLOSION");
		delay(500);
		r++;
		if(r%2==0)
		{
			c++;
		}
		
		
		if(r==23)
		{
			r=0;
			c=0;
		}
	}while(!kbhit());
	getch();
	return 0;
}
