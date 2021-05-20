# Pinos-Project-1-Threads
Requirements: Alarm Clock, Priority Schduling, Advanced Scheduler

## Code has been add like:
```
/* my code begins */
 MY CODE IS HEER
/* my code ends */
```

# Problem 1: Alarm Clock
## Project Requirements:
Reimplement timer_sleep(), defined in ‘devices/timer.c’. Although a working implementation is provided, it “busy waits,” that is, it spins in a loop checking the current time and calling thread_yield() until enough time has gone by. Reimplement it to avoid busy waiting.
```
void timer_sleep (int64 t ticks) [Function] Suspends execution of the calling thread until time has advanced by at least x timer ticks. Unless the system is otherwise idle, the thread need not wake up after exactly x ticks. Just put it on the ready queue after they have waited for the right amount of time. timer_sleep() is useful for threads that operate in real-time, e.g. for blinking the cursor once per second or for a RR scheduler.
The argument to timer_sleep() is expressed in timer ticks, not in milliseconds or any another unit. Do not change this value, because any change is likely to cause many of the tests to fail.
Separate functions timer_msleep(), timer_usleep(), and timer_nsleep() do exist for sleeping a specific number of milliseconds, microseconds, or nanoseconds, respectively, but these will call timer_sleep() automatically when necessary. You do not need to modify them.
```
The test cases you will need to successfully run for this part of the project are:
```
alarm-single
alarm-multiple
alarm-simultaneous
alarm-zero
alarm-negative 
```
You will find the expected output in

pintos/src/tests/threads/foo.ck

where foo is the name of the test.

These are also run when you execute make check. You may need to make clean on occasion.

## Modified Files:
1. `timer.c`
 - add `struct list sleeping_list;`
 - `timer_init();`
 - `timer_sleep();`
 - `timer_interrupt();`
2. `thread.c`
 - `thread_unblock();`
3. `thread.h`
 - add variable `int64_t wakeup_ticks;`
4. add function `thread_wakeup_ticks_less();`
