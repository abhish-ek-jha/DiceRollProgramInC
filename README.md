# DiceRollProgramInC
This Program rolls two dice and presents the total. It then asks the user to guess if the next total will be higher, lower, or equal. It then rolls two more dice and tells the user how they did.  
#include<stdio.h>
#include<stdlib.h>
#include<time.h>
#include<ctype.h>

int main()
{
     int dice1, dice2;
     int total1, total2;
     time_t t;
     char ans;
     //Remember that this is needed to make sure each random number generate dis different
     srand(time(&t));

     dice1 = (rand()%5) + 1;
     dice2 = (rand()%5)+1;
     total1 = dice1 + dice2;
     printf("First roll of the dice was %d %d ", dice1, dice2);
     printf("for a total of %d \n \n \n ",total1);
      do {
          puts("Do you think the nest roll will be");
          puts("Higher, Lower or same? \n");
          puts("Enter H,L or S to reflect your guess.");

          scanf("%c", &ans);
          ans=toupper(ans);
      }
      while((ans != 'H') && (ans != 'L') && (ans!='S'));

      //ROll the dice a secom=nd time to get your second total

      dice1=(rand()%5)+1;
      dice2=(rand()%5)+1;
      total2=dice1+dice2;

      //Display the second total for the user
      printf("\n The second roll was %d and %d ", dice1, dice2);
      printf("for a total of %d. \n\n", total2);

      //Now compare the dice totals against the user's guess
      //and tell them if they were right or not.

      if(ans=='L')
      {

           if(total2<total1)
           {
                printf("good job! You were right!\n");
                printf("%d is lower than %d \n", total2,total1);
           }
           else
           {
                printf("Sorry! %d is not lower than %d\n\n ", total2,total1);

           }
      }
        else if(ans=='H')
      {

           if(total2>total1)
           {
                printf("good job! You were right!\n");
                printf("%d is higher than %d \n", total2,total1);
           }
           else
           {
                printf("Sorry! %d is not higher than %d\n\n ", total2,total1);

           }
      }
       else if(ans=='S')
      {

           if(total2==total1)
           {
                printf("good job! You were right!\n");
                printf("%d is same as %d \n", total2,total1);
           }
           else
           {
                printf("Sorry! %d is not the same as %d\n\n ", total2,total1);

           }
      }
return 0;
}
