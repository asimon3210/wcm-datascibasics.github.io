## Chapter 1 Assignment

### Markdown
This is a markdown document (`.md`), a simple and easy-to-use markup language you can use to format most documents. You will be guided on how to use markdown while answering the prompts in this assignment, and you will find markdown especially useful for documenting your work in the future assignments (especially in Python or R). For now, use the `VSCode` editor (see course SetUp guide) to modify and complete the assignment, `VSCode` supports markdown files out of the box, and you can [preview](https://code.visualstudio.com/docs/languages/markdown#_markdown-preview) your markdown code with the rendered text side by side.

You will modify this file with your answers and submit your assignment in an email to `xix2007@med.cornell.edu`. The file should be saved as `{first}-{last}-assignment{#}.md`, and your email should be titled `datascibasics assignment {#}`.

### Assignment:
Follow chapter 1's [exercise module](https://axiezai.github.io/wcm_datasci_basics_01shell/05-assignment/) steps and answer the following questions:

#### Q1:
Explain in your own words, what the `datascibasics` script file you've created does when executed. Enter your answer in the markdown quoted block here:
> The `datascibasics` script file I made uses the `curl` command to transfer data from the URL https://wcm-datascibasics.github.io to my computer. The `--head` option in the script makes it so that only the header from the URL is transfered to my computer, and the `--silent` option makes the `curl ` command mute any progress meters or error messages. the `#!/bin/sh` at the beginning of the script file tells the shell which interpreter to use. In this case, it will use the `sh ` interpreter. 

#### Q2:
According to the output error message and permissions you listed in step 6, why doesn't your `datascibasics` script work?
> It didn't work when I wrote `./datascibasics ` because that command requires the execute permission bit for `datascibasics`. That command reads the `#!` line to determine how to execute the program.
#### Q3:
When you ran the same script with `sh` in step 7, why did this work?
> The  `sh` command only requires read permission for  `datascibasics`, as sh is specified as the command to execute the file. Thus, `sh` will ignore the `#!` line in the script. 

#### Q4a:
In steps 8 and 9, what permission combination did you change your `datascibasics` file to? Copy and paste the `chmod` command you used, and show the permissions of your file in the code block here:
```bash
# The chmod command you used: chmod 744 datascibasics 

# New file permissions as displayed in your terminal: -rwxr--r-- 1 asimon3210 asimon3210 57 Jan 31 21:04

```

#### Q4b:
what is the lowest numeric value your file permissions can have for the code to execute? What about the highest? Why do you think you should avoid giving the highest permissions to a script file (think on a shared machine, like a shared lab computer)?
> The lowest value your file permissions can have for the code to execute is 100. The highest is 777. You should avoid giving the highest permissions to a script file because it allows any person who opens it to have the ability to tamper with it as they please, or accidentally change/delete something important in it. You could lose some very important scripts/data. 

#### Q5:
Use `man` again to check out what the `cat` program does, and use it to view your `last-modified.txt` file from the last step. When is the last time our course website was modified?
```bash
# Answer with your terminal output here: last-modified: Thu, 28 Jan 2021 18:20:38 GMT

```

### Q6a:
The `history` program lists your command line history When you simply enter `history` into your terminal. The filtering options are different for `bash` and `zsh`. For `bash`, `history 20` will display the last 20 commands used in your `bash` history, whereas `history 1 20` in `zsh` displays the first 20 entries of your `zsh` history (You can use `history -20 -1` to display the last 20 commands). Use `history` to do the following:
```bash
# Display the last 10 commands you used in your terminal:
  647  cd /tmp/spring2021 /| grep -w "curl" datascibasics                                                                 
  648  cd /tmp/spring2021 \| grep -w "curl" datascibasics                                                                 
  649  cd /tmp/spring2021                                                                                                 
  650  ls -l |grep -w "curl" datascibasics                                                                                
  651  history 10                                                                                                         
  652  cd ~                                                                                                               
  653  cd /tmp/spring2021                                                                                                 
  654  ls -l |grep -w "curl" datascibasics                                                                                
  655  ./datascibasics                                                                                                    
  656  history 10 

# Use | and grep to display the commands that operates on your datascibasics file. 
cd /tmp/spring2021
ls -l |grep -w "curl" datascibasics
```

### Q6b:
The history program also lists a line number with each command recorded in your history. Select the line number from the history you displayed in `Q6a` that executes your shell script, enter an `!` in your terminal followed by the line number (`!52` if your line number was 52), what happens? 

Now, what if you wanted to recall and execute a command relative to our current position? For example, if our `./datascibasics` execution was 5 commands ago, how do we use `!` to use relative line numbers instead of absolute line numbers (hint: see the `zsh` instructions from part a)?
```bash
# When I run `!655`, the command from line 655 runs again. To use relative line numbers, you would use !-5 to recall and execute something 5 commands ago. 
```
