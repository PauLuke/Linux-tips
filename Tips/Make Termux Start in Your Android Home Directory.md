# Make Termux Start in Your Android Home Directory

Did you know Android is also based on Linux, right? So here’s a tip for those of you guys using Termux on Android.

By default, Termux uses a home directory that’s hidden deep in your phone's file system, which can make it tricky to access your files from a file manager. If you'd prefer Termux to start in your Android phone's main storage (the folder you usually see in your file manager), here's how to set that up:

## 1. Open Termux.

Go to Termux app and open it

Great addition! Here's a polished version of that section with clearer grammar, smoother flow, and formatting to match the tone and style of your tip:

---

## 2. Open your `.bashrc` file:

The `.bashrc` file lives in Termux's default home directory. If it doesn’t exist yet, no problem — you can create it using the `touch` command, or just open it directly with your favorite text editor, which will automatically create it for you if needed.

In this example, we'll use the **Micro** text editor:

```
micro ~/.bashrc
```

Obs.: If you don’t have Micro installed, you can install it with:

```
pkg install micro
```

## 3. At the end of the `.bashrc` file, add this line:

```
cd /storage/emulated/0/
```

## 4. Save and exit the editor.

Make sure you have saved the file before exiting.

## Explanation

What you're doing here is simply adding a command to your .bashrc file that opens the desired directory. The commands in .bashrc are executed automatically every time a new session starts, so from now on, when you open Termux, you'll land directly in `/storage/emulated/0/` (your phone's "home directory") — making it much easier to access and manage your files.

If you want to go back to Termux’s default home directory, just type `cd` and you will get there.
