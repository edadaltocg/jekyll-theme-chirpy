---
layout: post
title: "Useful shortcuts for VS-code to increase coding efficiency"
categories: Development
tags: productivity development VS-code
math: false
---

Install the VIM code extension inside vs code. Just search for `vim` in the extension search tool and it will be the first with millions of downloads.

Vim is a universe in itself. Some says it has a steep learning curve and others can't even exit the native code editor. I know that because I begin using nano in the command line because I couldn't exit a file out of vim.

However, its shortcuts and macros can help you A LOT when writing and refactoring coding. It is not about how fast you type, but how effective you can navigate and alter code on the editor.

By using vim shortcuts inside VS code you will get the best of both. A super Code editor with awesome shortcuts and combinations to fly inside the code.

So, let's wrap up the most useful commands here.

## Outside the text editor

These are the VSCode shortcuts that I actually use. They are easy to remember and handy.

Swap VS code tabs: `ctrl + tab`

Open settings: `ctrl + ,`

Find in files: `ctrl + shift + f`

Replace in files: `ctrl + shift + h`

## Vim basics

Vim has essentially 3 modes: `INSERT` mode, `NORMAL` model and `VISUAL` mode.

* `INSERT` mode let's you insert text normally, just like any other text editor. You enter this mode by pressing `i`.
* `NORMAL` mode is where the magic happens. You have access to commands and macros to navigate and also change your text/code content easily. You enter this mode by pressing `ESC`.
* `VISUAL` mode comes in handy when you want to visualize a piece of code in which you are going to move, delete or change. 

_Tip_: on VS Code you can bind these commands to something else if you find annoying pressing `ESC` all the time for example. I will show you in the end of the article. 

The following commands are available on `NORMAL` mode. This is not a full user manual, only a limited subset of commands that I use frequently and that I found useful for my workflow.

## Navigate your file

| Functionality                                   | Command |
| ----------------------------------------------- | ------- |
| Go to beginning of file                         | gg      |
| Go to end of file                               | G       |
| Recenter the cursor on the middle of the screen | zz      |

## Navigate the lines

| Functionality                                                  | Command          |
| -------------------------------------------------------------- | ---------------- |
| Move cursor to the above line                                  | k                |
| Move cursor to the line below                                  | j                |
| Move the entire line up or down                                | alt + arrow keys |
| Move the cursor to the beginning of the line                   | 0                |
| Move the cursor to the end of the line                         | $ (shift + 4)    |
| Move the cursor to the end of the line and enter `INSERT` mode | A                |
| Go to a specific line number                                   | : + line number  |
| Go up or down a block of code                                  | shift + { or }   |

## Navigate words 

| Functionality                                                               | Command            |
| --------------------------------------------------------------------------- | ------------------ |
| Move cursor to **b**eginning of word                                        | b                  |
| Move cursor to **e**nd of word                                              | e                  |
| Move cursor to next **w**ord                                                | w                  |
| Find a character in a line (useful to use with parentheses and other marks) | t + character      |
| Find a word on the file                                                     | / + word           |
| Find the next word on the text under the cursor                             | ctrl + 8 (*)       |
| Cycle through the found words                                               | n (down) or N (up) |

## Insert and remove content

| Functionality    | Command                         |
| ---------------- | ------------------------------- |
| Copy character   | y                               |
| Copy entire line | yy                              |
| Copy text        | select text (`VISUAL` mode) + y |
| Paste            | p                               |

## Vim tips and general commands

* Tip: you can prefix a command with a number to repeat that command a specific number of times.
  * Example: 
* Tip: press `.` to repeat the last command.

### General commands


### Insert content

Multiple characters:
    input example: 3i + - + ESC

    output: ---

Line above: O

Line below: o

Insert tab space: shift + >

Remove tab space: shift + <

Change one character under the cursor: r + character

Copy a line: yy

Paste below: p

Paste above: P

### Delete content

command: example: d + w (delete next word)

Tip: combine d + number to delete multiple content.

Delete an entire line: dd

Tip: dd copies the line to the clipboard.

change command: C -> deletes everything right to the cursor

Delete everything up until a character: c or d + t + character

Tip: use the above command with brackets {} ()

delete the character the cursor is in: x

### Find character or text

find on the same line: f + character

Tip: be careful when typing the character i because it will enter edit mode.

Find text: / + specific text

Tip: navigate through findings with n and N.

Find word in the cursor: shift + 8 (*)

### Brackets

Go to brackets surrounding a piece of code: shift + 5

## Visual mode (V or v (inline))

Useful to see what you are selecting to delete or execute other commands.

Useful to see what you are selecting to delete or execute other commands.