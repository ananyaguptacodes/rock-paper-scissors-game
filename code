#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int rockpaperscissor(char you, char comp)
{
    // returns 1 for win, -1 for lose and 0 for draw
    //  rr,pp,ss--> 0(draw)
    //  rp,ps,sr--> -1(lose)
    //  rs,pr,sp-> 1(win)
    if (you == comp)
    {
        return 0; // draw
    }
    if (you == 'r' && comp == 'p' || you == 'p' && comp == 's' || you == 's' && comp == 'r')
    {
        return -1; // lose
    }
    if (you == 'r' && comp == 's' || you == 'p' && comp == 'r' || you == 's' && comp == 'p')
    {
        return 1; // win
    }
}
int main()
{
    char you, comp;
    char playAgain;
    int draws = 0, wins = 0, losses = 0;
    srand(time(0));
    do
    {
        // generating computer's choice
        int number = rand() % 3; // generates 0,1 and 2
        if (number == 0)
            comp = 'r';
        else if (number == 1)
            comp = 'p';
        else
            comp = 's';
        printf("enter 'r' for rock, 'p' for paper and 's' for scissor\n ");
        scanf(" %c", &you);

        if (you != 'r' && you != 'p' && you != 's')
        {
            printf("Invalid input! Please choose amongst 'r','p' and 's'.\n ");
            continue; // skips the rest of loop and asks for input again
        }

        int result = rockpaperscissor(you, comp);
        printf("you chose '%c' and computer chose '%c'\n", you, comp);
        if (result == 0)
        {
            printf("Game draw\n");
            draws++;
        }
        else if (result == 1)
        {
            printf("Hurray!You win.\n");
            wins++;
        }
        else
        {
            printf("You lose.\n");
            losses++;
        }

        // asking the user if they want to play again
        printf("Do you want to play again? (y/n):\n");
        scanf(" %c", &playAgain);

        // ensure if the input is valid for replay
        while (playAgain != 'y' && playAgain != 'Y' && playAgain != 'n' && playAgain != 'N')
        {
            printf("Invalid input! Please enter 'y' for yes and 'n' for no.");
            scanf(" %c", &playAgain);
        }

    } while (playAgain == 'y' || playAgain == 'Y');

    printf("Final Scores-> Wins: %d, Losses: %d, Draws: %d\n", wins, losses, draws);
    printf("Thanks for playing! Goodbye.\n ");
    return 0;
}
