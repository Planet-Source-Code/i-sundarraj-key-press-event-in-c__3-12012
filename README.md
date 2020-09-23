<div align="center">

## KEY PRESS EVENT IN C


</div>

### Description

This program displays a clock.Importantly, this program won't prompt for any input, but it will respond to input's (in the form of key press events). Normally in c we can't get the input without prompting for it, but this program gets the input without prompting and proceeds accordingly.
 
### More Info
 
Enter the centre x and y value and the radius of circle.for eg, 200 200 120

Normally in c we can't get the input without prompting for it, but this program gets the input without prompting and proceeds accordingly.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[I\.SUNDARRAJ](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/i-sundarraj.md)
**Level**          |Advanced
**User Rating**    |5.0 (15 globes from 3 users)
**Compatibility**  |C
**Category**       |[Graphics/ Sound](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/graphics-sound__3-15.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/i-sundarraj-key-press-event-in-c__3-12012/archive/master.zip)

### API Declarations

```
#include&lt;graphics.h&gt;
#include&lt;stdio.h&gt;
#include&lt;conio.h&gt;
#include&lt;math.h&gt;
#include&lt;string.h&gt;
#include&lt;dos.h&gt;
```


### Source Code

```
int kk=90,kkk=90,kkkk=90,o=0,sta=0,cx=0,cy=0,clen=0,cclen=0,check=0,check1=-1,hour[10],min[10],sec[10],menuvar=0;
char sub[10][10];
float cval[25];
void mino(int k,int size)
{
int adj,opp;
if(k<=90&&k>=0)
{
adj=cval[k]*cclen;
opp=sqrt((cclen*cclen)-(adj*adj));
circle(cx+adj,cy-opp,size);
line(cx,cy,cx+adj,cy-opp);
}
if(k<180&&k>=90)
{
adj=cval[180-k]*cclen;
opp=sqrt((cclen*cclen)-(adj*adj));
circle(cx-adj,cy-opp,size);
line(cx,cy,cx-adj,cy-opp);
}
if(k<=270&&k>=180)
{
adj=cval[k-180]*cclen;
opp=sqrt((cclen*cclen)-(adj*adj));
circle(cx-adj,cy+opp,size);
line(cx,cy,cx-adj,cy+opp);
}
if(k<=360&&k>=270)
{
adj=cval[360-k]*cclen;
opp=sqrt((cclen*cclen)-(adj*adj));
circle(cx+adj,cy+opp,size);
line(cx,cy,cx+adj,cy+opp);
}
if(sta==0)
outtextxy(cx+4,cy,"AM");
else
outtextxy(cx+4,cy,"PM");
}
void disp()
{
int temp=0;
if(sta==1)
temp=12;
else
temp=0;
if(kkkk<=90&&kkkk>=0)
printf("\t\t%d:",((90-kkkk)/30)+temp);
else
printf("\t\t%d:",((450-kkkk)/30)+temp);
if(kkk<=90&&kkk>=0)
printf("%d:",(90-kkk)/6);
else
printf("%d:",(450-kkk)/6);
if(kk<=90&&kk>=0)
printf("%d",(90-kk)/6);
else
printf("%d",(450-kk)/6);
}
void value()
{
cval[0]=1.000000000;
cval[6]=.994521895;
cval[12]=.9781476;
cval[18]=.951056516;
cval[24]=.913545457;
cval[30]=.866025403;
cval[36]=.809016994;
cval[42]=.743144825;
cval[48]=.669130606;
cval[54]=.587785252;
cval[60]=.5000000000;
cval[66]=.406736643;
cval[72]=.309016994;
cval[78]=.20791169;
cval[84]=.104528463;
cval[90]=0.000000000;
}
void checking()
{
int limit4,limit3,limit2,count,lim4,lim3,lim2,lim1=0;
if((kkkk>=0)&&(kkkk<=90))
{
limit4=90;
lim4=0;
}
else
{
limit4=360;
lim4=3;
}
if((kkk>=0)&&(kkk<=90))
{
limit3=90;
lim3=0;
}
else
{
limit3=360;
lim3=15;
}
if((kk>=0)&&(kk<=90))
{
limit2=90;
lim2=0;
}
else
{
limit2=360;
lim2=15;
}
if(sta==1)
lim1=12;
for(count=0;count<10;count++)
{
if((hour[count]==(((limit4-kkkk)/30)+lim4)+lim1))
{
if((min[count]==(((limit3-kkk)/6)+lim3)))
{
if((sec[count]==(((limit2-kk)/6)+lim2)))
{
check1=count;
min[count]=-1;
check=1;
break;
}
}
}
}
}
void getting1(char ch)
{ int del,i,limi;
switch (ch)
{
case 's':
{
clrscr();
cleardevice();
for(i=0;i<10;i++)
{
if(min[i]==(-1))
{
printf("Enter the time");
scanf("%d%d%d%s",&hour[i],&min[i],&sec[i],sub[i]);
break;
}
}
if(i==11)
{
printf("full");
delay(10);
}
break;
}
case 'l':
{
clrscr();
cleardevice();
printf("\t\tTHE TABLE");
for(i=0;i<10;i++)
printf("\n\t\t %d %d %d %d %s",i,hour[i],min[i],sec[i],sub[i]);
outtextxy(150,380,"NOTE:IF ANY VALUE IS -1 THE CORRESPONDING ENTRY IS INVALID");
outtextxy(400,400,"PRESS ANY KEY TO QUIT");
getch();
break;
}
case 'd':
{
clrscr();
cleardevice();
printf("\t\tTHE TABLE");
for(i=0;i<10;i++)
printf("\n\t\t %d %d %d %d %s",i,hour[i],min[i],sec[i],sub[i]);
printf("\nENTER THE INDEX TO DELETE(Enter -1 to not del anything)");
scanf("%d",&del);
if((del<11)&&(del>=0))
min[del]=-1;
break;
}
case 'o':
{
if(menuvar==1)
{menuvar=0;
break;}
if(check1>=0&&check1<10)
{
min[check1]=-1;
check=0;
}
break;
}
case 'x':
{
clrscr();
cleardevice();
back:printf("\nENTER THE TIME");
scanf("%d%d%d",&kkkk,&kkk,&kk);
if(kkkk>23||kkk>59||kk>59)
{
clrscr();
cleardevice();
printf("\nENTER CORRECTLY");
goto back;
}
if(kkkk>=12)
{sta=1;
kkkk=kkkk-12;
}
else sta=0;
if(kk>=0&&kk<=15)
limi=-90;
else
limi=-450;
kk=abs(limi+kk*6);
if(kkk>=0&&kkk<=15)
limi=-90;
else
limi=-450;
kkk=abs(limi+kkk*6);
if(kkkk>=0&&kkkk<=3)
{if(kkkk==0)
o=0;
else
o=1;
limi=-90;
}
else
{
limi=-450;
o=0;
}
kkkk=abs(limi+kkkk*30);
break;
}
case 'm':
{
menuvar=1;
break;
}
case 'c':
{
clrscr();
cleardevice();
printf("ENTER THE (new)CENTER AND RADIUS");
scanf("%d%d%d",&cx,&cy,&clen);
break;
}
case 't':
{
disp();
}
case 'n':
{
break;
}
default:
{
clrscr();
cleardevice();
outtextxy(134,3,"INVALID");
delay(10);
}
}}
char getting()
{
int status;char cch;
asm{mov status,0X00;
mov ah,0X01;
int 0X16;
jz sun;
mov status,1;
mov cch,al;
}
sun: if(status==1)
{
asm{mov ah,0X00;
int 0X16;}return cch;
}
else
return 'n';
}
void menu()
{
outtextxy(300,300,"x:TO SET TIME");
outtextxy(300,310,"s:TO SET REMAINDER");
outtextxy(300,320,"d:TO DELETE A REMAINDER");
outtextxy(300,360,"e:TO EXIT");
outtextxy(300,330,"o:TO INFORM THAT U GOT THE REMAINDER");
outtextxy(300,340,"IF U PRESS o IT WONT SHOW THE SUB ANYMORE");
outtextxy(300,350,"ALSO IF THE MENU IS ON IT WILL BE OFFED");
outtextxy(300,370,"l:LISTS THE REMAINDERS MEM");
outtextxy(300,380,"c:CHANGES THE CLOCK SIZE");
outtextxy(300,400,"t:TO DISPLAY THE TIME");
}
void main()
{
int i,gd=DETECT,gm;
char g;
initgraph(&gd,&gm,"");
cleardevice();
for(i=0;i<10;i++)
min[i]=-1;
printf("ENTER CENTER AND RADIUS(above 25)");
scanf("%d%d%d",&cx,&cy,&clen);
setcolor(kkk);
circle(cx,cy,clen);
cclen=clen-15;
mino(kkkk,4);
cclen=clen-10;
mino(kkk,6);
cclen=clen-8;
mino(kk,8);
label:
value();
outtextxy(250,4,"KEY PRESS EVENT IN C");
for(i=0;i<=59;i++)
delay(20);
kk-=6;
cleardevice();
if(kkk%48==0)
setcolor(WHITE);
else
setcolor(kkk);
circle(cx,cy,clen);
cclen=clen-15;
mino(kkkk,4);
cclen=clen-10;
mino(kkk,6);
cclen=clen-8;
mino(kk,8);
checking();
if(check==1)
outtextxy(50,50,sub[check1]);
if(menuvar==1)
menu();
else
outtextxy(350,350,"press m to know the menu");
if(kk==90)
{o=1;
kkk-=6;
}
if((o!=0)&&kkk==90)
{
if(kkkk==120)
{
if(sta==0)
sta=1;
else
sta=0;
}
kkkk-=30;
o=0;
}
g=getting();
if(g=='e')
goto end;
getting1(g);
if(kk==0)
kk=360;
if(kkk==0)
kkk=360;
if(kkkk==0)
kkkk=360;
goto label;
end:
}
```

