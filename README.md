# notes
simple CLI notes-app, for quick-reference on the fly, like TLDR but with your own entries for faster lookup

Written while I was supposed to be studying for the RHCSA so this is my public reminder that I need to actually do that instead of tinkering with scripts)

Feel free to use/modify/share

~WR/Scotchman0


# notes - your local library of quick notes
 
notes are stored by default in ~/my-notes 
settings (like your default save path) and preferred editor/reader are managed in: ~/.notes.conf

# getting started with notes: 
1. clone this repository
2. make notes executable with $ sudo chmod a+x ./notes
3. copy or move notes into /usr/bin, or, add the install directory to your path for calling later:
> sudo export PATH=${PATH}:/path/to/this/executable
4. type 'notes' into commandline and press return to create the default conf variables and default save location, then modify ~/.notes.conf if desired. 
5. type 'notes -h' for help or 'notes example' for a welcome file example that provides options on getting started + basic usage.

USAGE:

> notes [options] [arguments]
 
options:
> -h, --help                show brief help
> 
> -f, --find=FIND           search for a subject string
> 
> -g, --grep=GREP STRING    search for any display matches inside library
> 
> -n, --new=NEW NOTE open default editor of choice at ~/my-notes/<note_name>

**note that you do not need to include .txt at the end of your notes (you certainly can, but when you call the file again with notes you'll need to provide the name including the .txt appendation. This may follow later, but generally it's not necessary to add this.
 
arguments:
search for strings inside your notes, or the names of the notes themselves
can also supply no options and supply the exact match of the file to read the whole thing
examples:
 
notes examples
> notes -f ex --> the following notes match this string: example ..." 
> 
> notes -g welcome= --> welcome to notes!"
> 
> notes -n new_note --> runs vi at /path/to/notes/new_note

try the command: 'notes example' for getting started
