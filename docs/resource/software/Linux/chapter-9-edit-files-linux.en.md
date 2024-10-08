---
comments: true
---

# Chapter 9: Editing Files in Linux Terminal

Learn about editing text files in the Linux terminal using the beginner friendly Nano editor in the second last chapter of this series.

You have learned a bunch of file operations so far in this Terminal Basics series. You learned to create new files, delete existing ones, and copy and move them.

It is time to take it to the next level. Let's see how to edit files in the Linux terminal.

If you are writing bash shell scripts, you can use the GUI text editors like Gedit and run them in the terminal.

But at times, you'll find yourself in a situation where you have to edit existing files in the terminal itself. For example, modifying config files located in the /etc directory.

As a desktop Linux user, you could still use GUI editors for editing config files even as root. I'll show it to you later.

However, knowing how to edit files in the command line is better.

## Editing files in Linux terminal

You may use the cat command if you just have to add a few lines at the bottom of an existing file. But in order to properly edit a file, you'll need a proper text editor.

There is simply no shortage of [terminal-based text editors in Linux](https://itsfoss.com/command-line-text-editors-linux/). **Vi, Vim, Nano, Emacs are just a few of the most popular ones** out there.

But here is the thing. All of them have a learning curve involved. You don't have the comfort of the GUI. You don't have menus to interact with the editor with your mouse.

Instead, **you have to use (and remember) keyboard shortcuts**.

I find Nano to be a good starting point for new users. It is the default text editor in Ubuntu and many other Linux distributions.

Of course, there is a learning curve, but it is not as steep as that of Vim or Emacs. It keeps on displaying the most relevant keyboard shortcuts at the bottom. This helps you navigate even if you don't remember the exact shortcut.

For this reason, I'll be covering the absolute basics of the Nano editor here. You’ll **learn all the essentials you need to know to start using Nano for editing files** in the Linux terminal.

## Using Nano editor

Nano can be used to edit text files, script files, program files etc. Please remember that **it is not a word processor** and cannot be used to edit docs or PDF files. For simple text editing of conf files, scripts, or text files, Nano is a great choice.

!!! question "🚧"

    You should have Nano installed on your system to follow this tutorial.

I'll be using a text file named agatha_complete.txt. It consists of the names of all Agatha Christie’s books under her name. You can download it from this link if you plan to follow the steps on your system.

https://itsfoss.com/content/files/2023/04/agatha_complete.txt

### Explore the Nano editor interface

Open the Nano editor with the following command:

```Bash
nano
```

You’ll notice a new interface in your terminal that reads like GNU nano and displays New Buffer. **New Buffer means Nano is working on a new file**.

This is equivalent to opening a new unsaved file in a text editor like Gedit or Notepad.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-nano-editor-interface.png)
*Nano editor interface*

Nano editor shows essential keyboard shortcuts you need to use for editing at the bottom of the editor. This way, you won’t get stuck at [exiting the editor like Vim](https://itsfoss.com/how-to-exit-vim/).

The wider your terminal window, the more shortcuts it shows.

You should get familiar with the symbols in Nano.

- **The caret symbol (^) means Ctrl key**
- **The M character mean the Alt key**

!!! note "📋"

    When it says `^X Exit`, it means to use `Ctrl+X` keys to exit the editor. When it says `M-U Undo`, it means use `Alt+U` key to undo your last action.

One more thing. It shows the characters in caps in the keyboard. But it doesn’t mean uppercase character. ^X means Ctrl + x key on the keyboard, not Ctrl+Shift+x key (to get the uppercase X).

You may also get a detailed help document inside the editor by pressing Ctrl+G.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-nano-detailed-help.png)
*Press Ctrl+G to bring up the help menu in Nano*

Now that you are a bit familiar with the interface, exit the Nano editor with Ctrl+X keys. Since you have not made any changes to this opened unsaved file, you won’t be asked to save it.

Awesome! You now have some ideas about the editor. In the next section, you’ll learn to create and edit files with Nano.

### Create or open files in Nano

You can open a file for editing in Nano like this:

```Bash
nano filename
```

If the file doesn’t exist, it will still open the editor and when you exit, you’ll have the option for saving the text to my_file.

You may also open a new file without any name as well (like new document) with Nano like this:

```Bash
nano
```

Try it. In a terminal, just write `nano` and enter.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-new-file-in-nano.png)
*New file in Nano*

Did you notice “New Buffer”? Since you did not give the file any name, it indicates that is a new, unsaved file in the memory buffer.

You can start writing or modifying the text straightaway in Nano. There are no special insert modes or anything of that sort. It is almost like using a regular text editor, at least for writing and editing.

If you make any changes to the file (new or existing), you’ll notice that an asterisk (*) appears beside the file name or New Buffer (meaning a new, unsaved file).

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-new-modified-file-in-nano.png)
*Asterisk means the file has unsaved changes*

That seems good. In the next section, you’ll see how to save files and exit the Nano editor interface.

### Saving and exiting in Nano

Nothing is saved immediately to the file automatically unless you explicitly do so. When you **exit the editor using Ctrl+X** keyboard shortcut, you’ll be asked whether you want to save the file.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-save-new-file-in-nano.png)

- **Y** to save the file and exit the editor
- **N** to discard changes
- **C** to cancel saving but continue to edit

If you choose to save the file by pressing the Y key, you’ll be asked to give the file a name. Name it my_file.txt.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-saving-new-file-in-nano.png)

!!! note "📋"

    The .txt extension is not necessary because the file is already a text file even if you do not use the extension. However, it is a good practice to keep the file extension for comprehension.

Enter the name and press the enter key. Your file will be saved and you’ll be out of the Nano editor interface. You can see that the text file has been created in your current directory.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-new-file-created-in-nano.png)

!!! note "📋"

    If you are habitual of using Ctrl+S for saving the file in a text editor and you subconsciously press that in Nano, nothing happens. Why “nothing happens” is important? Because if you press Ctrl+S in a Linux terminal, it freezes the output screen and you cannot type or do anything. You can get back from this “frozen terminal” by pressing Ctrl+Q.

### Perform a “save as” operation in Nano

In Gedit or Notepad, you get the “save as” option to save the changes made to an existing file as a new file. This way, the original files remain unchanged and you create a new file with the modified text.

You can do it in Nano editor too and the good thing is that you don’t need to remember another keyboard shortcut. You can use the same Ctrl+X keys that you used for saving and exiting.

Let’s see it in action. Open the sample file you had downloaded earlier.

```Bash
nano agatha_complete.txt
```

If you don’t make any changes, Ctrl+X will simply close the editor. You don’t want that, do you?

So just press enter and then backspace key. This will insert a new line and then delete it as well. This way, nothing in the text file is changes and yet Nano will see it as a modified file.

If you press Ctrl+X and press Y to confirm the save, you’ll come to the screen where it shows the file name. What you can do is to change the file name here by pressing the backspace key and typing a new name.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-save-as-different-file-in-nano.png)

It will ask you to confirm saving it under a different name. Press Y to confirm this decision.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-save-as-different-file-name-in-nano.png)

I named it agatha_complete.back as an indication that it is a “backup” of a file of the same name. It’s just for convenience. There is no real significance behind the .back extension.

So, you have learned to save files with Nano in this lesson. In the next section, you’ll learn to move around a text file.

### Moving around in a file

Open the agatha_complete.txt file with Nano. You know how to open files with Nano editor, right?

```Bash
nano agatha_complete.txt
```

Now you have a text file with several lines. How do you switch to other lines or to the next page or to the end of the line?

Mouse clicks don’t work here. **Use the arrow keys to move up and down, left and right**.

You can use the Home key or Ctrl+A to move to the beginning of a line and End key or Ctrl+E to move to the end of a line. Ctrl+Y/Page Up and Ctrl+V/Page Down keys can be used to scroll by pages.

- Use arrow keys for moving around
- Use Ctrl+A or Home key to go to the beginning of a line
- Use Ctrl+E or End key to go to the end of a line
- Use Ctrl+Y or Page Up keys to go up by one page
- Use Ctrl+V or Page Down keys to go down by one page

You have not made any changes to the file. Exit it.

Now, open the same file again but using this command:

```Bash
nano -l agatha_complete.txt
```

Did you notice something different? The `-l` option displays the line numbers in the left-hand side.

Why did I show that to you? Because I want you to learn to go to a specific line now. To do that, use Ctrl+_ (underscore) key combination.

!!! note "📋"

    The Help options get changed at the bottom. That’s the beauty of Nano. If you choose a special keyboard shortcut, it starts showing the options that can be used with that key combination.

In the above picture, you can enter a line or column number. At the same time, it shows that you can enter Ctrl+Y to go to the first line of the file (it is different from the regular Ctrl+Y for moving one page up).

Using Ctrl+T on the same screen, you can go to a certain text. That’s almost like searching for a specific text.

And that brings us to the topic of the next section, which is search and replace.

### Search and replace

You still have the sample text file opened, right? If not, open it again. Let’s how to to search for text and replace it with something else.

If you want to search for a certain text, **use Ctrl+W** and then enter the term you want to search and press enter. The cursor will move to the first match. To go to the next match, **use Alt+W keys**.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-nano-search-text.png)

By default, the search is case-insensitive. You can perform a case-sensitive search by pressing Alt+C when you are about to perform a search.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-nano-case-sensitive-search-text.png)

Once again, look at the bottom for options that can be used. Also note that it shows the last searched term inside brackets.

Similarly, you can also use regex for the search terms by pressing **Alt+R**.

And lastly, **use Ctrl+C to come out of search mode**.

If you want to replace the searched term, **use Ctr+\ keys** and then enter the search term and press enter key.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-nano-search-replace-text.png)

Next, it will ask for the term you want to replace the searched items with.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-nano-replace-text.png)

The cursor will move to the first match and Nano will ask for your conformation for replacing the matched text. Use Y or N to confirm or deny respectively. Using either of Y or N will move to the next match. You may also use A to replace all matches.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-nano-replaced-text.png)

In the above text, I have replaced the second occurrence of the term Murder with Marriage and then it asks whether I want to replace the next occurrence as well.

**Use Ctrl+C to stop the search and replace.**

You have made some changes to the text file in this lesson. But there is no need to save those changes. Press Ctrl+X to exit but don’t go for the save option.

In the next section, you’ll learn about cut, copy and paste.

### Cut, copy and paste text

Open the sample text file first.

!!! question "💡"

    If you don’t want to spend too much time remembering the shortcuts, use the mouse.

Select a text with mouse and then use the right click menu to copy the text. You may also use the Ctrl+Shift+C [keyboard shortcut in Ubuntu](https://itsfoss.com/ubuntu-shortcuts/) terminal. Similarly, you can use the right click and select paste from the menu or use the Ctrl+Shift+V key combination.

Nano also provides its own shortcuts for cutting and pasting text but that could become confusing for beginners.

Move your cursor to the beginning of the text you want to copy. Press Alt+A to set a marker. Now use the arrow keys to highlight the selection.

Once you have selected the desired text, you can Alt+6 key to copy the selected text or use Ctrl+K to cut the selected text. Use Ctrl+6 to cancel the selection.

Once you have copied or cut the selected text, you can use Ctrl+U to paste it.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-nano-cut-copy-paste.png)

If you do not want to continue selecting the text or copying it, use Alt+A again to unset the mark.

To recall:

- You can use Ctrl+Shift+C to copy and Ctrl+Shift+V to paste the content of the clipboard in most Linux terminals.
- Alternatively, use Alt+A to set the marker, move the selection using arrow key and then use Alt+6 to copy, Ctrl+k to cut and Ctrl+6 to cancel.
- Use Ctrl+U to paste the copied or cut text.

Now you know about copy-pasting. The next section will teach you a thing or two about deleting text and lines in Nano.

### Delete text or lines

There is no dedicated option for deletion in Nano. You may use the Backspace or Delete key to delete one character at a time. Press them repeatedly or hold them to delete multiple characters. Just like in any regular text editor.

You can also use the Ctrl+K keys that cuts the entire line. If you don’t paste it anywhere, it’s as good as deleting a line.

If you want to delete multiple lines, you may use Ctrl+K on all of them one by one.

Another option is to use the marker (Ctrl+A). Set the marker and move the arrow to select a portion of text. Use Ctrl+K to cut the text. No need to paste it and the selected text will be deleted (in a way).

### Undo and redo

Cut the wrong line? Pasted the wrong text selection? It’s easy to make such silly mistakes and it’s easy to correct those silly mistakes.

You can undo and redo your last actions using:

- **Alt+U : Undo**
- **Alt+E : Redo**

You can repeat these key combinations to undo or redo multiple times.

## Almost the end...

If you find Nano overwhelming, you should try Vim or Emacs. You'll start liking Nano.

[Basic Vim Commands Every Linux User Must Know [With PDF Cheat Sheet]](https://linuxhandbook.com/basic-vim-commands/?)

This is a good starting point for Emacs. Give it a try if you want.

[Basic Emacs Command Explained in Detail](https://linuxhandbook.com/basic-emacs-guide/?)

No matter how beginner-friendly Nano is, some people may find the idea of editing important files in the terminal intimidating.

If you are using Linux desktop where you can access a GUI editor, you can use it to edit those important files as root.

Say, you have Gedit installed on your system and you have to edit the SSH config file as root. You can run Gedit as root from the terminal like this:

```Bash
sudo gedit /etc/ssh/ssh_config
```

It will open a Gedit instance as root. The command keeps on running in the terminal. Make your changes and save the file. It will show warning messages when you save and close Gedit.

![](https://cdn.jsdelivr.net/gh/SDNURoboticsAILab/ImageBed@master/img/resources/linux/chapter9-using-gedit-to-edit-config-files.png)

We are almost at the end of our terminal basics series. In the tenth and the last chapter of the series, you'll [learn about getting help in the Linux terminal](https://itsfoss.com/linux-command-help/).

For now, let me know in the comment section if you encounter any issues.

>via: [https://itsfoss.com/edit-files-linux/](https://itsfoss.com/edit-files-linux/)
>
>Author: [Abhishek Prakash](https://itsfoss.com/author/abhishek/)
