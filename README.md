# notes
simple CLI notes-app, for quick-reference on the fly, like TLDR but with your own entries for faster lookup

Written while I was supposed to be studying for the RHCSA so this is my public reminder that I need to actually do that instead of tinkering with scripts)

Feel free to use/modify/share

~WR/Scotchman0


# notes - your local library of quick notes
 
notes are stored by default in ~/bin/reference (this is the $path variable which can be set by modifying the script)

USAGE:

> notes [options] [arguments]
 
options:
> -h, --help                show brief help
> 
> -f, --find=FIND           search for a subject string
> 
> -g, --grep=GREP STRING    search for any display matches inside library
> 
> -n, --new=NEW NOTE open default editor of choice in ~/bin/reference/<note_name>
 
arguments:
search for strings inside your notes, or the subjects of the notes themselves
can also supply no options and supply the exact match of the file to read
examples:
 
notes example
> notes -f nmcli_ --> did you mean nmcli_examples, nmcli_standards
> 
> notes -g DNS1= --> file: nmcli-standards: HWADDR=... ==> 802-3-ethernet.mac-address ...
> 
> notes -n new_note --> runs vi at path to new_note
> 
> notes example ---> 'neat' 
