# Overview

This is a basic C program that reads a playlist from an input text file named ``playlist.txt`` and turns it into a singly linked list. This is done so that it is possible to add, edit, or remove the songs on the playlist and output the new playlist as ``playlist-out.txt``.
I have only written the parts wrapped by ``MY CODE START`` and ``MY CODE END``.

## Example output

The required output of the program can be seen in the ``playlist-out.txt`` file.

# Files

## main.c

Explanations of the code blocks I have written:

### Inside ``remove_newline_if_exists()``

As the name suggests, this function is responsible for removing trailing carriage returns ``\r`` and newlines ``\n`` if they are present in the input line.

### Inside ``load_file()``

This function opens the file specified in the ``filename`` argument and the checks for errors when doing this.
It continuously reads lines from the passed file, removes trailing newlines, and copies the line to the data field of a new node in the linked list.
If the list is empty, the head of the list is set to be the new node, otherwise the function traverses to the end of the list and appends the new node there.
The function keeps doing this as long as there are lines to read from the passed file.
The file is then closed and the finished list is returned.

### Inside ``save_file()``

This function opens the file specified in the ``filename`` argument and then checks for errors when doing this.
It then loops throught the list given in the ``list`` argument and writes every list element to the passed file, separated by newlines.