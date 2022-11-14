# Lab Report 4

## Part 1: changing `start` to `base`

Sequence: `/star<Enter>cebase<Esc>ninini:wq`

Total: 22 characters pressed

Sequence in Images:

`/star + <ENTER>`

![star](https://media.discordapp.net/attachments/1023749314587140137/1041531521443569764/image.png)

I started at the top of the file for this. Then, using the `/` command, which searches for a pattern, I searched for `star` for "start", and then it jumped to the first instance of "start", because nothing else matches in the file. This took 5 keypresses total.

Then, I pressed `<ENTER>` to exit out of searching for the pattern.

`"c" + "e" `

![ce](https://media.discordapp.net/attachments/1023749314587140137/1041531631237861417/image.png)

As learned in class, `"c" + "e"` changes the file up until the end of the word. In the image, it shows deleting "start", then entering INSERT mode so I can change it to something else. Total: 2 keys pressed.

`"b" + "a" + "s" + "e"`

![base](https://media.discordapp.net/attachments/1023749314587140137/1041531711034494987/image.png)

This command is what "start" should be changed to. In this case, it was "base". Since vim is already in INSERT mode, then I just have to type it in. Total: 4 keys pressed

`<ESC>`

![esc](https://media.discordapp.net/attachments/1023749314587140137/1041531766751645807/image.png?width=799&height=339)

This command takes me out of INSERT mode and back into vim NORMAL mode. Total: 1 key pressed.

`n`

![n](https://media.discordapp.net/attachments/1023749314587140137/1041531808489144391/image.png)

This command iterates through the occurences of the pattern searched for , which is "start". In this image, it was iterated to the next time "start" appears. Total: once per iteration, three iterations.

`i`

![i](https://media.discordapp.net/attachments/1023749314587140137/1041531919902441482/image.png)

This command takes the `cebase` used in insert mode and applies it to whatever is highlighted. Here, it is seen that `start.toFile();` was changed to `base.toFile(); Total: once per iteration, three iterations.

`":" + "w" + "q"`

![:wq](https://media.discordapp.net/attachments/1023749314587140137/1041535746533765252/image.png?width=799&height=354)

These three keys are vim's command line. When `:` is pressed in NORMAL mode, vim starts to take arguments that won't affect how the file is written. `w` writes the file and saves it with the new changes, and `q` exits vim. Total: 3 keys pressed.

# Part 2:

## Editing in VSCode and then using `scp`

Time Elapsed: 2:42

I was having difficulties because I wasn't typing in the command correctly, and I kept making mistakes because my `scp` command wasn't correctly formatted.

## Editing in remote SSH

Time Elapsed: 1:17

This was easier because I didn't have to scp or log into the remote server to run it. All I had to do was edit in vim, then exit vim and run `bash test.sh`, which made it significantly easier to type, with less room for errors in typos.

## Concluding questions

If I were running a program remotely, I'd prefer to use vim to edit in remote SSH, because it's a hassle to keep exiting and entering the server, as well as remembering to scp every time you make a change to the code. If all I had to do was edit once and send it over, I wouldn't mind using VSCode. Also, if the file was really big, I'd rather do it on the server rather than take all of that and do it on both computer and server, which is an unnecessary annoyance.
