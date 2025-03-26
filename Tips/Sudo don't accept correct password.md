# Sudo don't accept correct password

So, you're typing the correct password, but sudo is acting as if it's incorrect? In my experience, a common cause for this issue is running a command like paru or yay and forgetting about it.
This happens because these programs may require your password, prompting you to enter it, but you might not notice the prompt. By default, pam_faillock.so is enabled to lock out users for 10 minutes after three failed login attempts within a 15-minute period. If you failed to enter your password three times, you might have been locked out.

How do you fix this? Simply run:

```
faillock --user username --reset
```
