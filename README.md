# demo #include <stdio.h>
#define MAE 220


int getline(char line[], int maxline);
void reverse(char longest[], char to[], int lim);

main()
{
        int len;
        int max;
        char line[MAE];
        char longest[MAE];


        max=0;
        while((len=getline(line,MAE))>0)
                printf("%s",line);

                reverse(line,longest, len);
                printf("%s",longest);
                printf("%s",line);
        return 0;
}

int getline( char s[],int lim)
{
        int c,i;

        for (i=0; i<lim-1 && (c=getchar()) !=EOF && c!='\n';++i)
                s[i]=c;

        if (c== '\n'){
                s[i]=c;
                ++i;
        }
        s[i]='\0';
        return i;
}

void reverse(char to[],char from[], int lim)
{
        int i;


        i=0;
        while(lim>=0){
                to[i]=from[lim-2];
                ++i;
                --lim;
        }
        from[i]='\n';

        from[i+1]='\0';

}



