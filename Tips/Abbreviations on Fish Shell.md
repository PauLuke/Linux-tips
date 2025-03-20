# Abbreviations on Fish Shell

## 1. Why abbreviations instead of aliases?
The difference between an alias and an abbreviation is that the latter expands to the entire command when activeted. Traditionally, aliases are shown as they are typed in the shell’s history. The expansion is an excellent benefit of using abbreviations. One can always see the actual command behind the shorthand version. This is both useful for remembering the actual command and significant when sharing commands with others (such as in screenshots of the terminal), as they do not have to decode the aliases.

## 2. How to create a abbreviation?
I suggest the creation of a new file to store your abbreviations, because a separate file makes it easier to manage them.

Create an `abbreviations.fish` file in `~/.config/fish/conf.d`. We do that because any file in the `~/.config/fish/conf.d` directory will be automatically loaded in a standard fish setup.

Below is the content of my file:

```
abbr up "paru && flatpak update"
```

As you can see, the syntax is: the abbr command, followed by the abbreviation you would like to use and, finally, the actual command it should expand to.

Credits: https://layer22.com/fish-abbreviations
