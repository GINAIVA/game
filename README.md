#include <stdio.h> 
#include <stdlib.h> 
#include <time.h>

# define MAX_TRY 10
 

int main() 
{
	int randomNumber, guess, i;
	int score = 100;
	srand (time(NULL));
	randomNumber = rand () % 100 + 1;
	
	
	for (i = 0; i < MAX_TRY; i++) {
		puts ("Make a guess:");
		fscanf (stdin, "%d", &guess);
		if (randomNumber > guess) 
			fprintf (stdout, "%s", (i == MAX_TRY-1)? "":"Go up!\n");
				else if (randomNumber < guess) 
					fprintf (stdout, "%s", (i == MAX_TRY-1)? "":"Go down\n");
					else {
					fprintf (stdout, "Congratulations! You win! The number is %d. Your score is: %d\n", randomNumber, score);
					break;};
					score -= 10;
					
	}
		
		if (randomNumber != guess) fprintf (stdout, "Sorry! You fall! The Number is %d\n", randomNumber);
		
	/*fprintf (stdout, "%d\n", rand () % 10000000);
	srand (time(NULL));
	fprintf (stdout, "%d\n", time (NULL) );

	fprintf (stdout, "%d", rand () % 100);*/
	
	return 0;
}
