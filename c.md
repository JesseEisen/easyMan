# C

## erase current printed line

    \33[2K erases the entire line your cursor is currently on
    \033[A moves your cursor up one line, but in the same column i.e. not to the start of the line
    \r brings your cursor to the beginning of the line (r is for rewind) but does not erase anything

## sleep

    #include<time.h>
    nanosleep(const struct timespec *req, struct timespec *rem);

    struct timespec {
        time_t tv_sec;
        long   tv_nsec;
    }

 1000ns = 1us 
 1000us = 1ms
 1000ms  = 1s
