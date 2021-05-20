# Pinos-Project-1-Threads
Requirements: Alarm Clock, Priority Schduling, Advanced Scheduler

## Code has been add like:
/* my code begins */
 MY CODE IS HEER
/* my code ends */

# Problem 1: Alarm Clock
## Project Requirements:

void timer_sleep (int64 t ticks) [Function] Suspends execution of the calling thread until time has advanced by at least x timer ticks. Unless the system is otherwise idle, the thread need not wake up after exactly x ticks. Just put it on the ready queue after they have waited for the right amount of time. timer_sleep() is useful for threads that operate in real-time, e.g. for blinking the cursor once per second or for a RR scheduler.
The argument to timer_sleep() is expressed in timer ticks, not in milliseconds or any another unit. Do not change this value, because any change is likely to cause many of the tests to fail.
Separate functions timer_msleep(), timer_usleep(), and timer_nsleep() do exist for sleeping a specific number of milliseconds, microseconds, or nanoseconds, respectively, but these will call timer_sleep() automatically when necessary. You do not need to modify them. 
