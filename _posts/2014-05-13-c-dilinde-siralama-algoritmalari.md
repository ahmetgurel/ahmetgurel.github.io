---
layout: post
title: C Dilinde Sıralama Algoritmaları
date: 2014-05-13 13:19
author: ahmetgurel
comments: true
categories: [algoritma, BUBBLE SORT ALGORITMASI, C, c, c de sıralama algoritması, INSERTION SORT ALGORITMASI, SELECTION SORT ALGORITMASI, Sıralama algoritması]
---
<div class="separator" style="clear: both; text-align: center;"></div>
<div class="separator" style="clear: both; text-align: center;"></div>
<div class="separator" style="clear: both; text-align: center;"></div>
&nbsp;

&nbsp;
<div class="separator" style="clear: both; text-align: center;"><a style="clear: left; float: left; margin-bottom: 1em; margin-right: 1em;" href="http://3.bp.blogspot.com/--jcjO80cEWo/UxDHDFc8hPI/AAAAAAAAAMI/3_kwx64XNpo/s1600/1.gif"><img src="http://3.bp.blogspot.com/--jcjO80cEWo/UxDHDFc8hPI/AAAAAAAAAMI/3_kwx64XNpo/s1600/1.gif" alt="" border="0" /></a><a style="margin-left: 1em; margin-right: 1em;" href="http://3.bp.blogspot.com/-8Bv1tN9CTkI/UxDHC_Y_uFI/AAAAAAAAAME/sa3Q0yrNSoE/s1600/2.gif"><img class="alignnone" title="sıralama algoritmaları" src="http://3.bp.blogspot.com/-8Bv1tN9CTkI/UxDHC_Y_uFI/AAAAAAAAAME/sa3Q0yrNSoE/s1600/2.gif" alt="" width="86" height="320" border="0" /></a></div>
&nbsp;
<pre style="font-family: Andale Mono, Lucida Console, Monaco, fixed, monospace; color: #000000; background-color: #eee; font-size: 12px; border: 1px dashed #999999; line-height: 14px; padding: 5px; overflow: auto; width: 100%;"><code>/*  Ahmet GÜREL
Süleyman Demirel University Yazılım Kulübü | Yönetim Kurulu Üyesi
Süleyman Demirel University| Computer Engineering
www.gurelahmet.com| www.eternusyazilim.com
ahmet5794@gmail.com | ahmetgurel.yazilim@gmail.com */

#include <stdio.h>
#include <stdlib.h>
#include <conio.h>

//---- BUBBLE SORT ALGORITMASI ----//
void bubble(int array[],int size)
{
    int i,j,temp;
    for(i=1;i&lt;size;i++)
    {
        for(j=0;j&lt;size-i;j++)
        {
            if(array[j]&gt;array[j+1])
            {
                temp=array[j+1];
                array[j+1]=array[j];
                array[j]=temp;
            }   
        }       
    }
   
   
    for(i=0;i&lt;size;i++)
        printf("%d ",array[i]);
}


//---- SELECTION SORT ALGORITMASI ----//
void selection(int array[],int size)
{
    int i,j,temp,min;
   
    for(i=0;i&lt;size-1;i++)
    {
        min=i;
        for(j=i+1;j&lt;size;j++)
        {       
            if(array[j]&lt;array[min])
                min=j;
        }   
        temp=array[i];
        array[i]=array[min];
        array[min]=temp;
    }
   
    for(i=0;i&lt;size;i++)
        printf("%d ",array[i]);   
}

//---- INSERTION SORT ALGORITMASI ----//
void insertion(int array[],int size)
{
   
    int i,j,temp;
   
    for(i=0;i&lt;size;i++)
    {
        for(j=0;j&lt;i+1;j++)
        {
            if(array[j]&gt;array[i])
            {
                temp=array[i];
                array[i]=array[j];
                array[j]=temp;
            }
        }       
    }
   
    for(i=0;i&lt;size;i++)
        printf("%d ",array[i]);   
}



int main(int argc, char *argv[]) {
    int dizi[]={9,4,6,2,8,1};
   
    bubble(dizi,6);
    puts("");
    selection(dizi,6);
    puts("");
    insertion(dizi,6);
    getch();
    return 0;
}


</code></pre>
