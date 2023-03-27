# notes
simple CLI notes-app, for quick-reference on the fly, like TLDR but with your own entries for faster lookup

Feel free to use/modify/share/contribute

~WR/Scotchman0

# notes - your local library of quick notes
 
notes are stored by default in ~/my-notes 

settings (like your default save path) and preferred editor/reader are managed in: ~/.notes.conf

you can edit the file directly with `notes settings`

# Options you can configure:
- Reader selection: uses CAT by default to print to cli, but can update to any other binary/executable or option set like 'glow -p' 'less' 'xdg_open' 'firefox' for example
- editor: defaults to vi for universal access, but can be updated to anything that can write to text: nano, subl, etc
- default file extension (default null) can define that notes save as markdown, txt, log, etc. 
- path to save notes in: defaults to ~/my-notes/ but you can redirect this anywhere more convenient like a common directory or secure log location.


# getting started with notes: 
1. clone this repository
2. make notes executable with $ sudo chmod a+x ./notes
3. make a softlink in ~/bin:
> ln -s ~/path/to/github/notes/notes ~/bin/notes

this makes the executable 'notes' immediately available if ~/bin is a part of your $PATH

4. type 'notes' into commandline and press return to create the default conf variables and default save location, then modify ~/.notes.conf if desired. 
5. type 'notes -h' for help or 'notes example' for a welcome file example that provides options on getting started + basic usage.

# updating notes:
1. delete ~/.notes.conf
2. run a git pull command: $ sudo git pull
3. call the command 'notes' if you've added the download location to your $PATH variable, or run locally: ./notes
4. it will replace ~/.notes.conf with an updated version (this is important -variables have been modified in versions v5 and later).
5. use notes like normal, and reference 'notes -h' for updated use list as applicable.

# USAGE:

> notes [options] [arguments]

> settings                  opens the ~/.notes.conf file for modifications
 
> -h, --help                show brief help
> 
> -l, --list= LIST NOTES    list all note titles (tab doesn't populate until next shell launch)
> 
> -g, --grep=GREP STRING    greps match + 2 lines following in library (-i is enabled so not exact match)
> 
> -n, --new=NEW NOTE/edit   opens in <note_name> with editor selection (appends filetype selection if defined in settings)
> 
> -e, --edit                opens <note_name> with editor selection (does not append filetype selection in case you have mixed file appendations)
>
> -d, --delete              deletes note: notes -d <note_name> --> (ask to confirm=true)
> 
> -d! --delete!             delete without asking: notes -d! <notename>  --> (deleted)
>
> [notename]                print contents of note to cli (or open less|subl|reader if you've modified this option in ~/.notes.conf)


 
 ![Screenshot_20210824_122451](https://user-images.githubusercontent.com/35974491/130654524-59f26288-1fba-44a8-b461-162695795020.png)

 
arguments:
search for strings inside your notes, or the names of the notes themselves
can also supply no options and supply the exact match of the file to read the whole thing
examples:
 
# notes examples
> notes <name_of_note> --> cat contents of <name_of_note> (default behavior)
> 
> notes -g welcome= --> welcome to notes!"
> 
> notes -n new_note --> runs vi or your editor binary/app at ~/my-notes/new_note

try the command: 'notes example' for getting started


# tab auto-completion:

I have implemented a line in the ~/.notes.conf file that will enable tab completions following 'notes' command to reference the library. 
However, it is sourced at shell launch, (which means your tab-list will only refresh when you launch a new shell session for now. use notes -l to see all notes if you don't want to leave session to refresh) and requires an appendation to your ~/.bashrc or ~/.zshrc profile:

to enable tab completion simply follow the prompts during first time use, or if setting up later:

> echo ". ~/.notes.conf" >> ~/.bashrc
 
 
 # EXAMPLE of quick recall/match/grep features:
 
![Screenshot_20210824_122737](https://user-images.githubusercontent.com/35974491/130654683-d4eb0a44-6300-4509-9d38-e08c88211d09.png)
