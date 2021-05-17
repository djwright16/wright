//dominic wright
//10 may 2021
// lab 11
//c program 

#include <stdio.h>
#include <ctype.h>

int main(){
char ans, ch, input[200];
int i=0, ws=0, a=0, b=0,c=0;
    do {
        printf("This program calculates the number of whitespace characters, \nnumber of digits, number of lowercase and uppercase letters.\n\n");
        printf("It then converts your message to uppercase/lowercase once you have entered \nz which the program reads as your submission.\n\n");
        printf("So, without further ado, please enter the message you would like to run through our magical machine.\n");
            while((ch=getchar())!='z'){
                input[i]=ch; 
                    if(ch==' '){// index is whitespace
                        ws++; 
                    }
                    if(ch > 47 && ch < 58){ // when index is digit
                        a++; 
                    }
                    if(ch > 64 && ch < 91){
                        b++; 
                        input[i] = ch + 32; // converting index to lowercase
                    }
                    if(ch > 96 && ch < 123) {
                        c++; 
                        input[i] = ch - 32; // converting index to Uppercase
                    }
                i++;
    }
    input[i]='\0';

    printf("# of whitespace characters: %d\n", ws);
    printf("# of digits: %d\n", a);
    printf("# of lowercase characters: %d\n", c);
    printf("# of uppercase characters:%d\n\n", b);
    printf("LOADING...\n"); 
    printf("Your output after being processed in our magical machine:\n");
        printf("%s\n", input);
    printf("Would you like to do another message? (Y or N)\n");
        scanf("%s", &ans); 
        if (ans == 'N' || ans =='n'){
            printf("\tBye! Come back again!\n");
                printf("\t\tSession terminated, system will self destruct in 5, 4, 3, 2, 1 (just kidding)"); 
        }
    }while (ans == 'Y' || ans == 'y');
}
    
