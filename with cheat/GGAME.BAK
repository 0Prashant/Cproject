#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
#include<dos.h>
#include<time.h>
const int width=75;
const int height=20;
char maze,pp=0,name[20];
int i,j,k,d=219,cheat,speed=20,retail,cheat;
int gameover,print=0,level,p;
int linex[100]={15,15,15,15,15,15,15,15,15,15,0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,60,60,60,60,60,60,60,60,60,60,53,54,55,56,57,58,59,60,61,62,63,64,65,66,67,68,69,70,71,72,73,74,75,76,77,28,29,30,31,32,33,34,35,36,37,38,39,40,41,42,43,44,45,46,47,38,38,38,38,38,38,38};
int liney[100]={0,1,2,3,4,5,6,7,8,9,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,0,1,2,3,4,5,6,7,8,9,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,14,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,5,13,14,15,16,17,18,19};
int x,y,fruitx,fruity,score;
int tailx[100],taily[100];
int ntail=0;
int dir,xxx,yyy,flagg;
struct scoree
	{
	char name[20];
	int score;
	};
union REGS ii,oo;
void callmouse()
	{
	ii.x.ax=1;
	int86(0x33,&ii,&oo);
	}
int clickk()
	{
	int click;
	ii.x.ax = 3;
	int86(0x33,&ii,&oo);
	click=oo.x.bx;
	return click;
	}
void mousehide()
	{
	ii.x.ax=2;
	int86(0x33,&ii,&oo);
	}
void sett(int *a, int *b)
	{
	ii.x.ax=3;
	*a=oo.x.cx;
	*b=oo.x.dx;
	int86(0x33,&ii,&oo);
	}
void mouse()
{
int a,b,click;
clrscr();
callmouse();
gotoxy(30,9);
printf("!! SNAKE GAME !!");
	printf("\n\n\t\t\t\t START");
	printf("\n\t\t\t\t EXIT");
do
	{
	click=clickk();
	sett(&a,&b);
	gotoxy(10,3);
     /*	printf("position : (%d,%d)\n",a,b);
	printf("         click:%d",click); */
	if (a>=264&&a<=303&&b>=80&&b<=86&&click==1)
		break;
	else if(a>=264&&a<=294&&b>=87&&b<=93&&click==1)
		{
		gameover=1;
		break;
		}
	else
		continue;
	}while(!kbhit());
mousehide();
}
void setup()
	{
	gameover = 0;
	dir = 0;
	fruitx=rand()%width;
	fruity=rand()%height;
	x=width/2-8;
	y=height/2;
	score = 0;
	}
void loading()
	{
	int a=177,b=219,i,j;
	clrscr();
	gotoxy(30,11);
		for(j=0;j<=20;j++)
			{
			printf("%c",a);
			}
	gotoxy(30,11);
	for(i=0;i<=20;i++)
		{
		gotoxy(25,10);
		printf("         LOADING   %d%",(i*5));
		gotoxy(30+i,11);
		printf("%c",b);
		sound(1000);
		delay(50);
		nosound();
		delay(50);
		}
	getch();
	sound(1000);
	delay(50);
	nosound();
	}
welcome()
	{
	char a[17]={"WELCOME TO THE"};
	char b[15]={"C-PROGRAMMING"};
	char c[15]={"SNAKE GAME"};
	gotoxy(33,10);
	for (i=0;i<=14;i++)
		{
		if(kbhit())
			break;
		sound(1000);
		printf("%c",a[i]);
		delay(50);
		nosound();
		delay(100);
		}
	printf("\n\t\t\t        ");
	for (i=0;i<=14;i++)
		{
		if(kbhit())
			break;
		sound(1000);
		printf("%c",b[i]);
		delay(50);
		nosound();
		delay(100);
		}
	printf("\n\t\t\t         ");
	for (i=0;i<=10;i++)
		{
		if(kbhit())
			break;
		sound(1000);
		printf("%c",c[i]);
		delay(50);
		nosound();
		delay(100);
		}
	getch();
	fflush(stdin);
	sound(1000);
	delay(100);
	nosound();
	return 0;
	}

void input()
	{
	if(kbhit())
		{
		dir=0;
		switch (getch())
		{
		case 'a':
			dir = 1;
			break;
		case 'd':
			dir = 2;
			break;
		case 'w':
			dir = 3;
			break;
		case 's':
			dir = 4;
			break;
		case 'x':
			gameover=1;
			break;
		}
		fflush(stdin);
		}

	}
void logic()
	{
	int px=tailx[0],py=taily[0],p2x,p2y;
	tailx[0]=x;
	taily[0]=y;
	retail = ntail;
	for(i=1;i<=ntail;i++)
		{
		if ((x==tailx[i])&&(y==taily[i])&&(cheat==0))
			{
			gameover=1;
			}
		p2x=tailx[i];
		p2y=taily[i];
		tailx[i]=px;
		taily[i]=py;
		px=p2x;
		py=p2y;
		}
	switch(dir)
		{
		case 1:
			{
			if (x>1)
				x--;
			}
			break;
		case 2:
			{
			if (x<width+2)
				x++;
			}
			break;
		case 3:
			{
			if (y>1)
				y--;
			}
			break;
		case 4:
			{
			if (y<height +2)
				y++;
			}
			break;
		}
		if (((x<=0)||(x>=width+2)||(y<=1)||(y>=height+2))&&(cheat==0))
			{
			gameover = 1;
			ntail=0;
			}
		 if((maze=='m')||(maze=='M'))
		 {
		for(p=0;p<100;p++)
			{
			if(x==linex[p]+1&&y==liney[p]+2&&(cheat==0))
				gameover=1;
			}
		}
		if ((x==fruitx)&&(y==fruity))
			{
			ntail=ntail+1;
			score+=10;
			if(speed>0)
				speed=speed-1;
			do
				{
				flagg=0;
				fruitx=rand()%72+2;
				fruity=rand()%18+2;

				for(j=0;j<100;j++)
					{
					if(((fruitx==linex[j])&&(fruity==liney[j]))||fruitx==0||fruity==0)
						{
						flagg=1;
						break;
						}
					}
				}while (flagg==0);
			sound(200);
			delay(100);
			nosound();
			}
	}
void draw()
	{
	clrscr();
	for (i=0;i<width+2;i++)
		{
		printf("%c",d);
		}
	for (i=0;i<height;i++)
		{
		for (j=0;j<=width;j++)
			{
			pp=0;
			if(j==0)
				{
				printf("\n%c",d);
				}
			else
				{
				print=0;


				if (print==0)
					{
					printf(" ");
					}
				}
			if (j==width)
				{
				printf("%c",d);
				}
			}
		}
	printf("\n");
	for (i=0;i<width+2;i++)
		printf("%c",d);
	printf("\n\nScore = %d \t\t\t\t\t Press X to quit the game",score);
	}
void mdraw()
	{
	clrscr();
	for (i=0;i<width+2;i++)
		{
		printf("%c",d);
		}
	for (i=0;i<height;i++)
		{
		for (j=0;j<=width;j++)
			{
			pp=0;
			if(j==0)
				{
				printf("\n%c",d);
				}
			else
				{
				print=0;


				for(p=0;p<100;p++)
				{
				if(((i==liney[p])&&(j==linex[p]))&&pp!=1)
					{
					printf("%c",d);
					print=1;
					}
				if((x==linex[p])&&(y==liney[p]))
					{
					gameover=1;
					}
				}
				if (print==0)
					{
					printf(" ");
					}
				}
			if (j==width)
				{
				printf("%c",d);
				}
			}
		}
	printf("\n");
	for (i=0;i<width+2;i++)
		printf("%c",d);
	printf("\n\nScore = %d \t\t\t\t\tPress X to quit the game",score);
	}
void sprint()
	{
	gotoxy(xxx,yyy);
	printf(" ");
	gotoxy(x,y);
	xxx=x,yyy=y;
	printf("%c",2);
	if (dir!=0)
		{
		sound(2000);
		delay(10);
		nosound();
		}
	gotoxy(fruitx,fruity);
	printf("%c",4);
	for(k=0;k<ntail;k++)
		{
		gotoxy(tailx[k],taily[k]);
		printf("o");
		gotoxy(tailx[ntail],taily[ntail]);
		printf(" ");
		}
	gotoxy(1,24);
	printf("Score = %d   \t\t\t\t\tPress X to quit the game",score);
	switch(level)
			{
			case '1':
				delay(speed*6);
			case '2':
				delay(speed*5);
			case '3':
				delay(speed*4);
			case '4':
				delay(speed*3);
			case '5':
				delay(speed*2);
			}
	}
   void scorr()
   {
	struct scoree s[100],temp;
	int i,j,n;
	char ch;
	FILE *fp;
	clrscr();
	fp=fopen("ggg.txt","a");
	if(fp==NULL)
	{
		puts("cannot read the directed file");
		exit (1);
	}
   fprintf(fp,"%s",name);
   fputs(" ",fp);
   fprintf(fp,"%d",score);
   fputs("\n",fp);
   fclose(fp);
   fp=fopen("ggg.txt","r");
   if(fp==NULL)
	{
		puts("cannot read the directed file");
		exit (1);
	}
   n=0;
   while(!feof(fp))
	{
	fscanf(fp,"%s",&s[n].name);
	fscanf(fp,"%d",&s[n].score);
	n++;
	}
for(i=0;i<n-1;i++)
	{
	for(j=i+1;j<n;j++)
		{
		if(s[j].score>s[i].score)
			{
			temp=s[i];
			s[i]=s[j];
			s[j]=temp;
			}
		}
	}
   printf("The top 5 players are listed below\n");
   for(i=0;i<5;i++)
	{
	printf("\n%10s \t:-%5d",s[i].name,s[i].score);
	}
   fclose(fp);
   getch();
}

void main()
	{
	mouse();
	loading();
	clrscr();
	gotoxy(25,11);
	printf("Please enter your name :-");
	fflush(stdin);
	gets(name);
	fflush(stdin);
	clrscr();
	welcome();
	clrscr();
	top:
	gotoxy(25,10);
	printf("\n\t\t     If you want to play in maze, press m\n\t\t     If you want to play in box, press b :- ");
	maze=getch();
	sound(1000);
	clrscr();
	gotoxy(25,10);
	printf("\n\t\t\t    Enter level from 1 to 5  \n\t\t\t\t    :- ");
	delay(100);
	nosound();
	level=getch();
	fflush(stdin);
	sound(1000);
	delay(100);
	nosound();
	setup();
	restart:
	dir = 0;
	clrscr();
	if((maze=='m')||(maze=='M'))
		mdraw();
	else
		draw();
	while(gameover!=1)
		{
		rand();
		sprint();
		input();
		logic();
		}
	sound(100);
	delay(1000);
	nosound();
	getch();
	clrscr();
	gotoxy(30,10);
	printf("\tGAME OVER\n   \t\t\t%s Your score is = %d",name,score);
	switch(getch())
		{
		case 'p':
			gameover=0;
			cheat = 1;
			goto restart;
		}
	sound(1000);
	delay(100);
	nosound();
	clrscr();
	scorr();
	clrscr();
	gotoxy(20,10);
	sound(1000);
	printf("\n\t\t\tDo you want to continue? Press y\n\t\t\tOtherwise press any key :- ");
	delay(100);
	nosound();
	speed = 20;
	switch(getch())
		{
		case 'y':
			{
			gameover=0;
			ntail=0;
			sound(1000);
			delay(100);
			nosound();
			goto top;
			}
		default:
			sound(1000);
			delay(100);
			nosound();
		}
	}