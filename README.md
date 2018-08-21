# CS50-pset1-less.c
Finds the minimum number of coins required to make any given amount of change. 
#include <stdio.h>
#include <cs50.h>
#include <string.h>
#include <stdlib.h>
#include <math.h>

int main (void)
{
    //receives user input
    float ammount;
    do{
        printf("How much money do you need to make change for?\n");
        ammount = get_float();
        ammount = round(ammount*100);
    }
    while(ammount <1);

    //calculate # of quarters
    int quarters =0;
    while (ammount >= 25){
        quarters +=1;
        ammount = ammount- 25;
    }

    //calculate # of dimes
    int dimes =0;
    while (ammount > 10){
        dimes +=1;
        ammount = ammount - 10;
    }

    //calculate the number of nickels
    int nickels = 0;
    while (ammount > 5){
        nickels +=1;
        ammount = ammount - 5;
    }

    //calculate the number of pennies
    int pennies = 0;
    while (ammount >= 1){
        pennies +=1;
        ammount = ammount - 1;
    }

    //prints the number of each type of coin used
    printf("%i quarters \n", quarters);
    printf("%i dimes \n", dimes);
    printf("%i nickels\n", nickels);
    printf("%i pennies\n", pennies);

    //prints the total number of coins used
    int total_coins = (quarters+dimes+nickels+pennies);
    printf("total coins: %i\n", total_coins);
}
