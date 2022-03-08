# mec4124f_prac3_mlxana001
prac 3
// Description----------------------------------------------------------------|
/*
 * Turns on the board LEDs
 */
// DEFINES AND INCLUDES-------------------------------------------------------|

#define STM32F051                                                  //COMPULSORY
#include <stdio.h>
#include "stm32f0xx.h"											   //COMPULSORY
#include "lcd_stm32f0.h"

// GLOBAL VARIABLES ----------------------------------------------------------|
typedef struct
{
	int date;
	int month;
	int year;
	int age;
}age_data;


// FUNCTION DECLARATIONS -----------------------------------------------------|

void main(void);                                                   //COMPULSORY

// MAIN FUNCTION -------------------------------------------------------------|

void main(void)
{
	init_LCD();
	age_data s1= {28, 8, 2000, 21};
	char anas[50];


	while(1)
	{
		for(int x=0;x<=s1.age;x++)
		{

			sprintf(anas,"%d",x);
			lcd_putstring(anas);
			delay(500000);
			lcd_command(CLEAR);
		}

	}

}

// OTHER FUNCTIONS -----------------------------------------------------------|

