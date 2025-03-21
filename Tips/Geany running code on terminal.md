# Geany running code on terminal

To make Geany run your code using the terminal, you can configure it by changing the "Terminal" setting in Geany's preferences. Here's how you can do that:

Go to: Edit > Preferences > Tools > Terminal

kitty --hold bash -c "chmod +x %c && %c"
