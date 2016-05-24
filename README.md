# countdown_cpp
countdown_cpp


```

//main.c
#include <stdio.h>      /* printf */
#include <time.h>       /* time_t, struct tm, difftime, time, mktime */
#include <unistd.h>
int main(){

	time_t timer;
	
	time(&timer);
	struct tm y2k = {0};
	double seconds;

	y2k.tm_hour = 0;   y2k.tm_min = 0; y2k.tm_sec = 0;
  	y2k.tm_year = 147; y2k.tm_mon = 6; y2k.tm_mday = 1;

	
	while(seconds >0){
		time(&timer);
		seconds = difftime(mktime(&y2k),timer);
		printf ("%.f seconds to July 1, 2047 in the current timezone\n", seconds);
		sleep(1);
	}
	return 0;
}

```
