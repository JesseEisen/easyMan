## string 

### regex

  need include `regex.h` and `sys/types.h`, and the API is 
  
    int regcomp(regex_t *preg, const char *regex, int cflags);
    int regexec(const regex_t *preg, const char *string, size_t nmatch, regmatch_t pmatch[], int eflags);
    size_t regerror(int errcode, const regex_t *preg, char *errbuf, size_t errbuf_size);
    void regfree(regex_t *preg);


 `Example`
    
    regex_t re;
    regmatch_t m[1];

    regcomp(&re, pattern, flags);
    regexec(&re,string,size, m, 0);
    memcpy(buf,&string[m[0].rm_so],m[0].rm_eo - m[0].rm_so); //get the total match

 
  if want to get all the match, can set the `regexec` function's third parameter as `1`. And in a loop.


### strtok_r

    char **
    split(char *raw, const char *delim){
        char *token, *saveptr;
        char **res;
        int i = 0;

        res = malloc(sizeof(char *)*1);

        for(;;raw = NULL){
            token = strtok_r(raw, delim, &saveptr);
            if(token == NULL) break;
            res[i++] = token;
            res = realloc(res, sizeof(char *) * (i+1));
        }

        res[i] = NULL;
        return res;
    }


