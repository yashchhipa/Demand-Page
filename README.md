# Demand-Page

Question 2:
Consider a scenario of demand paged memory. Page table is held registers. It takes 8 milliseconds to service a page fault if an empty page is available or the replaced page is not modified
and 20 milliseconds if the replaced page is modified. Memory access time is 100 nanoseconds. Assume that the page to be replaced is modified 70 Percent of the time. Generate a solution to find maximum acceptable page-fault rate for access time that is not more than 200 nanoseconds.

Solution-


Time taken to service a page fault if replaced page is not modified  (PFSTM)      = 8 milliseconds.          8*10^6 nanoseconds                                                                                

Time taken to service a page fault if replaced page is modified      (PFSTNM)       = 20 milliseconds. 20*10^6 nanoseconds

Maximum access time     (MAT)                                     = 100 nanoseconds.                                            	

Effective access time      (EAT)               = 200 nanoseconds.

Percentage of modification of page to be replaced      (PM)        = 70%                   =0.7	

Percentage of no modification of page to be replaced   (PNM)   = (1-PM) = (1-.7) = 0.3

Let us consider page fault rate =  P.



Formula to be used.

Effective access time    =   page fault rate[(Percentage modification*(time taken to service a page fault(replaced page is modified)))+(Percentage no modification*(time taken to service page fault(replaced page is not modified)))]  + (1-page fault rate)*Maximum Access Time                 


EAT = P[(PM*(PFSTNM))+(PNM*(PFSTM))]   +   (1-P)*MAT.


200 = P[(0.7*(20*10^6))+(0.3*(8*10^6))]	+ (1-P)*100.


200 = 100 [P[(14.0*10^4)+(2.4*10^4)] + (1-P)]


2   = P[16.4*10^4] + (1-P)


2   = 164000P - P  + 1


1   = P(164000-1)



1   = P(163999)


P   = 1/163999  =    6.1*10^-6   ANSWER.

#C Code

 /*Consider a scenario of demand paged memory. Page table is held registers. It takes 8 milliseconds to service a page fault if
 
  an empty page is available or the replaced page is not modified and 20 milliseconds if the replaced page is modified.
   
  Memory access time is 100 nanoseconds. Assume that the page to be replaced is modified 70 Percent of the time. 
  
  Generate a solution to find maximum acceptable page-fault rate for access time that is not more than 200 nanoseconds.*/

#include<stdio.h>

#include<math.h>

int main()

{

int PFSTNM=8*pow(10,4),PFSTM=20*pow(10,4),MAXAT=1,EAT=2;

//PFSTNM =   time taken to service a page fault(replaced page is Not modified)

//PFSTM  =   time taken to service a page fault(replaced page is modified

//MAXAT  =	 Maximum Access time

//EAT    =	 Effective Access time

float  PM=0.7;       // Percentage of modification of page

float a =(1-PM);     

	float PNM =a;         // percentage of no modification in page

/* Effective access time = page fault rate[(Percentage modification*(time taken to service a page fault(replaced page is modified)

))+(Percentage no modification *(time taken to service page fault(replaced page is not modified)))]  + 

(1-page fault rate)*Maximum Access Time                 */

printf("Percentage of no modification in page is: %f \n",PNM);

int result1=(PM*PFSTM);

int result2 =(PNM*PFSTNM);

int result3=(result1+result2);

float result4=(EAT- MAXAT);

double result5=result3-1;

double result6 = (result4/result5);

printf("maximum acceptable page-fault rate is: %lf",result6);

}




