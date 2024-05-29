# notes
simple CLI notes-app, for quick-reference on the fly, like TLDR but with your own entries for faster lookup

Feel free to use/modify/share/contribute

~WR/Scotchman0

# notes - your local library of quick notes
 
notes are stored by default in ~/my-notes 

settings (like your default save path) and preferred editor/reader are managed in: ~/.notes.conf

you can edit the file directly with `notes settings`

# Options you can configure:
`notes settings` to open the settings panel and change the following:
- Reader selection: uses CAT by default to print to cli, but can update to any other binary/executable or option set like 'glow -p' 'less' 'xdg_open' 'firefox' for example
- editor: defaults to vi for universal access, but can be updated to anything that can write to text: nano, subl, etc
- default file extension (default null) can define that notes save as markdown, txt, log, etc. 
- path to save notes in: defaults to ~/my-notes/ but you can redirect this anywhere more convenient like a common directory or secure log location.

Example config setup:
~~~
mypath=~/my-notes #where you will save notes for query (leave out the trailing slash)
myeditor=vim #default editor for creating new notes with -n option
myreader=less #cat is default, can change to any other view option like less|subl|glow|<your_reader_app> - accepts quoted commands
pathlength="$(echo $mypath/ | wc -m)" #trims the start of the path so that -k only shares filenames
notes_extension= #left blank (default) can update a default for easy export - accepts .md|.log|.txt|etc
~~~


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

`notes {options} {note-name}`


~~~
 settings                  opens the ~/.notes.conf file for modification
 -h, --help                show brief help
 -l, --list= LIST NOTES    list all note titles (tab doesn't populate until next shell launch)
 -g, --grep=GREP STRING    greps match + 2 lines following in library (-i is enabled so not exact match)
 -k, --search              searches for string match (use quotes) and displays note titles with positive hit
 -n, --new=NEW NOTE/edit   opens ${editor} in /home/sunbro/my-notes/<note_name> (sets a filetype extension if set in settings)
 -e, --edit                opens ${editor} in /home/sunbro/my-notes/<note_name> but does not append a filetype extension
 -d, --delete              deletes note: notes -d <note_name> --> (ask to confirm=true)
 -d! --delete!             delete without asking: notes -d! <notename>  --> (deleted)
 -p  --print | print       prints content of note directly to stdout instead of opening it with a reader for copy/paste

examples: 
`notes -n testnote` #create (or edit) a note named: `testnote`
`notes settings` #open settings panel for adjusted configuration options

~~~
 
 ![Screenshot_20210824_122451](https://user-images.githubusercontent.com/35974491/130654524-59f26288-1fba-44a8-b461-162695795020.png)
 

try the command: 'notes example' for getting started



# tab auto-completion:

I have implemented a line in the ~/.notes.conf file that will enable tab completions following 'notes' command to reference the library. 
However, it is sourced at shell launch, (which means your tab-list will only refresh when you launch a new shell session for now. use notes -l to see all notes if you don't want to leave session to refresh) and requires an appendation to your ~/.bashrc or ~/.zshrc profile:

to enable tab completion simply follow the prompts during first time use, or if setting up later:

> echo ". ~/.notes.conf" >> ~/.bashrc
 
 
 # EXAMPLE of quick recall/match/grep features:
 
![Screenshot_20210824_122737](https://user-images.githubusercontent.com/35974491/130654683-d4eb0a44-6300-4509-9d38-e08c88211d09.png)
