---
title: Why does my file have funny characters in it?
---

## {{ page.title }}

One of the most common problems that people come across when moving files
between different computer systems is that their line endings seem to be
destroyed. In this article, Dave Cross looks at this problem and suggests
some simple solutions.

---

### Introduction

If it hasn’t happened to you at some point then I can almost guarantee that
it will in the future. You transfer a text file from a DOS/Windows system
to a Unix system using FTP and every line has gained extra `^M` characters;
or you transfer a text file the other way only to find that all the lines
have run together and where the line endings were there is a strange black
rectangle.

You have become a victim of the non-standardisation of line endings across
different operating systems.

### What are line endings?

When you edit a text file in your favourite editor, whether it is an HTML
page, the source code of a computer program, a poem or a shopping list, you
press the Return (or Enter) key at the end of each line. This really changes
nothing in the meaning of the file (your browser would still be able to
display HTML that all appeared on one line) it merely makes it easier for you
(or other humans) to read the file.

When you press the enter key, the computer needs to mark the point in the
file where the line break occurs. It does this by inserting a special
character (strictly speaking, at least one special character) into the file
at this point. When displaying or printing the file for you in the future,
the editor knows that the special character means “don’t display this
character, but display the character after this on a new line”.

The problem occurs when you try to define which special characters to use.
There are two characters in the standard ASCII character set that might be
used for this purpose, the line feed (LF) character with ASCII code 10 and
the carriage return (CR) character with ASCII code 13. There is really very
little real choice between these two characters, but a choice must be made
when designing an operating system.

Of course, just because one set of operating system designers choose one
particular character, it doesn’t mean that all subsequent operating system
designers will agree with their decision. Herein lies our problem. The three
most used operating systems today are Unix (in all of its varients –
including Linux), Windows and MacOS and just to keep things as complex as
possible, they all use different line end characters. Here is a table showing
which characters the various systems use.

Line end characters on the three most popular operating systems

| OS | Line End |
|----|----------|
| Unix | LF |
| Windows/DOS | CR/LF |
| MacOS | CR |

As you can see, this selection just about covers all possibilities. Unix and
MacOS both choose a different one of the characters and Windows is greedy and
insists on them both (and notice that they must be in the order given, CR
before LF). Armed with this knowledge we can begin to explain what goes wrong
when you move a text file from its native operating system.

### Moving Text Files

It is important to note that a text file when stored on disk does not contain
the text formatted into lines. The lines are stored in one long stream of
binary data. It is only when the text is displayed (in an editor or by
printing the file) that the special line end characters are interpreted in a
manner that will reformat the text into lines.

Normally when you move a text file onto another operating system the binary
data is left untouched (that ‘normally’ hints at a solution which we will come
to in more detail later). Let’s examine what happens in some common cases and
see if we can explain the problems described above.

### Windows to Unix

Imagine a Unix editor (like vi or emacs) opening a text file that was created
under Windows. The text characters in the first line are all interpreted
correctly. At the end of the line, we find a CR. This means nothing special
to Unix so the editor attempts to display the character. CR is a
non-printable character, which means that it has no obvious visual
representation. Under Unix many of these non-printable characters are mapped
to control characters when displayed. In the case of CR, its displayable
equivalent is Control-M. This is displayed in most editors as `^M`.

The next character is a LF. Unix has no problems with this character as it is
the standard line end character. The editor therefore moves to the start of
the next line on the display and starts to process the next line.

In this way you can see that the file will be displayed with an extra `^M` at
the end of each line, but with the line endings intact.

Imagine now a Windows editor (like Notepad) trying to display a text file
that was created under Unix. The text characters in the first line are all
interpreted correctly. At the end of the first line the editor finds a LF
character. Under Windows this is not a valid line end character as it was not
preceded by a CR. The editor therefore just prints the character.
Unfortunately, LF is a non-printable character and in most Windows editors, a
non-printable character is displayed as a black rectangle.

The editor now moves on to the second line in the file and finds more normal
text characters. As there has been no CR/LF combination to indicate the end
of the line, the editor just prints the next line straight after the black
rectangle.

As the editor moves through the file it displays each line straight after the
previous one, separated only by the black rectangle that represent the
unprintable LF character.

### Macintosh Transfers

Hopefully you can now see how these problems are caused. I’ll leave it to you
to think about what will happen when Unix or Windows files are transfered to
a Macintosh.

### Problems Caused

So how much of a problem does this cause?

It depends really on what you were planning to do with the file. If it was
intended for humans to read, then obviously something needs to be done to fix
the formatting. On the other hand, if it was intended for machine consumption
(like a HTML page or program source code) then you might find that the broken
line endings don’t matter. If your program gives unexpected results then it
might be worth investigating wherther the input files have come from another
system and might be suffering from this problem.

### Solutions

There are a number of ways to get round or fix this problem. In increasing
order of complexity, they are:

#### Fixing the file in an editor

If you have a broken file and you want to fix it quickly, it may be possible
to fix it using your editor. Certainly on Unix, most editors are powerful
enough to fix this problem. For example if you have the file open in vi, you
can fix the problem by entering the following command.

    :1,$/^M//g

(You can enter the `^M` character by holding down the control key whilst
pressing M at the same time.)

I’m not sure if this option is open to you on Windows or MacOS, certainly
Notepad doesn’t have the capability to fix this problem. If anyone can give
any more information on this, then please let me know.

####  Fixing the file during transfer

Remember earlier when I said that when moving files to another operating
system, the binary data in the file was normally unaltered. Well, it is
possible to fix the data during transfer, depending on the transfer method
you use.

The most common way to move files between different systems is by using File
Transfer Protocol (or FTP). FTP is a widely implemented protocol for moving
files from one computer to another. You access FTP by using an FTP client
program. This might be a command line program that is just called FTP or a
GUI-based drag and drop program like WS-FTP or Cute FTP. If you transfer the
file using an FTP client you can put the client into ASCII transfer mode.
This means that all line endings will be converted to the correct type for
the target system during the transfer. A tutorial into using FTP clients is
beyond the scope of this article but it is worth noting that many newer FTP
clients have the ability to automatically change transfer mode depending on
the extension of the file being transfered. You may need to configure the
client to understand that more esoteric extensions are, in fact, text files.

Sometimes you don’t need to explicitly transfer files from one system to
another. Simply moving the file to another directory on the the same system
is enough. This is because the directory is cross-mounted from another
system. In this way it is possible to see Unix directories from a Windows
machine. The most common method for achieving this is using something like
the Network File System (NFS). Obviously, with NFS you can’t change the
transfer mode as there isn’t a transfer as such. It is, however, often
possible to configure NFS to automatically switch into ASCII mode depending
on the extension of the file.

#### Fixing the file with software

Some Unix varients come complete with filter programs called `dos2unix` and
`unix2dos` which will handle the conversions for you. They are implemented
as filters to make them as flexible as possible. From the command line, they
are invoked as follows.

    dos2unix < DOS_file.txt > Unix_file.txt

If your operating system doesn’t have these filters then it is easy enough to
create them in your favourite language. Here is an example of `dos2unix`
written in Perl.

    #!/usr/local/bin/perl -w
    use strict;

    while (<STDIN>) {
      s/\r\n/\n/;
      print;
    }

### Conclusions

This is certainly becoming one of the the most common problems that I see
discussed on Usenet. It has become much more prevalent now that people create
many files on Windows machines and then transfer them up to their Internet
Service Provider’s system which is probably running Linux or some other Unix
varient.

I hope that by explaining the problem and suggesting some solutions I can
help to stop too much time from being wasted discussing this simple problem.
