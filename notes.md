# 260-Notes ([markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax))

## The Console
### SSH 
```
ssh -i ~/desktop/260-website.pem ubuntu@bestwebsight.click
```
### Executing commands

- **echo** - Output the parameters of the command
- **cd** - Change directory
- **mkdir** - Make directory
- **rmdir** - Remove directory
- **rm** - Remove file(s)
- **mv** - Move file(s)
- **cp** - Copy files
- **ls** - List files
- **curl** - Command line client URL browser
- **grep** - Regular expression search
- **find** - Find files
- **top** - View running processes with CPU and memory usage
- **df** - View disk statistics
- **cat** - Output the contents of a file
- **less** - Interactively output the contents of a file
- **wc** - Count the words in a file
- **ps** - View the currently running processes
- **kill** - Kill a currently running process
- **sudo** - Execute a command as a super user (admin)
- **ssh** - Create a secure shell on a remote computer
- **scp** - Securely copy files to a remote computer
- **history** - Show the history of commands
- **ping** - Check if a website is up
- **tracert** - Trace the connections to a website
- **dig** - Show the DNS information for a domain
- **man** - Look up a command in the manual

You can also chain the input and output of commands using special characters

- `|` - Take the output from the command on the left and _pipe_, or pass, it to the command on the right
- `>` - Redirect output to a file. Overwrites the file if it exists
- `>>` - Redirect output to a file. Appends if the file exists

For example, you can list the files in a directory, pipe it into `grep` to search for files created in Nov, and then pipe that into `wc` to count the number of files found with a date of Nov.

```
ls -l | grep ' Nov ' | wc -l
```

There are also keystrokes that have special meaning in the console.

- `CTRL-R` - Use type ahead to find previous commands
- `CTRL-C` - Kill the currently running command

## Vim
### The Basics of Movement
- **h** moves the cursor one character to the left.
- **j** moves the cursor down one line.
- **k** moves the cursor up one line.
- **l** moves the cursor one character to the right.
- **0** moves the cursor to the beginning of the line.
- **$** moves the cursor to the end of the line.
- **w** moves forward one word.
- **b** moves backward one word.
- **G** moves to the end of the file.
- **gg** moves to the beginning of the file.
- **`.** moves to the last edit.
- **i** enters __insert mode__.

Here’s a handy tip: prefacing a movement command with a number will execute that movement multiple times.

### Editing
- **u** will undo the last operation.
- **Ctrl-r** will redo the last undo.
- **x** deletes the character that the cursor is on.
- **d** starts the delete operation.
- **dw** will delete a word.
- **d0** will delete to the beginning of a line.
- **d$** will delete to the end of a line.
- **dgg** will delete to the beginning of the file.
- **dG** will delete to the end of the file.

### Searching and Replacing
- **/_text_** search for text in the document, going forward.
- **n** move the cursor to the next instance of the text from the last search. This will wrap to the beginning of the document.
- **N** move the cursor to the previous instance of the text from the last search.
- **?text** search for text in the document, going backwards.
- **:%s/text/replacement text/g** search through the entire document for text and replace it with replacement text.
- **:%s/text/replacement text/gc** search through the entire document and confirm before replacing text.
#### Copying and Pasting
- **v*** highlight one character at a time.
- **V** highlight one line at a time.
- **Ctrl-v** highlight by columns.
- **p** paste text after the current line.
- **P** paste text on the current line.
- **y** yank text into the copy buffer.

### Saving and Quitting (in Last-Line Mode)
- **Esc** exits __insert mode__.
- **:** enters last __last-line mode__.
- **w** will write the file to the existing filename. If you don’t have a filename or want to write out to a different filename, use **:w _[filename}_**.
- **q** quits without saving.
- **q!** quits after saving.
- ZZ saves and quits outside of __last-line mode__.

## HTML

### Common elements

Modern HTML contains over 100 different elements. Here is a short list of HTML elements that you will commonly see.

| element   | meaning                                                                |
| --------- | ---------------------------------------------------------------------- |
| `html`    | The page container                                                     |
| `head`    | Header information                                                     |
| `title`   | Title of the page                                                      |
| `meta`    | Metadata for the page such as character set or viewport settings       |
| `script`  | JavaScript reference. Either a external reference, or inline           |
| `include` | External content reference                                             |
| `body`    | The entire content body of the page                                    |
| `header`  | Header of the main content                                             |
| `footer`  | Footer of the main content                                             |
| `nav`     | Navigational inputs                                                    |
| `main`    | Main content of the page                                               |
| `section` | A section of the main content                                          |
| `aside`   | Aside content from the main content                                    |
| `div`     | A block division of content                                            |
| `span`    | An inline span of content                                              |
| `h<1-9>`  | Text heading. From h1, the highest level, down to h9, the lowest level |
| `p`       | A paragraph of text                                                    |
| `b`       | Bring attention                                                        |
| `table`   | Table                                                                  |
| `tr`      | Table row                                                              |
| `th`      | Table header                                                           |
| `td`      | Table data                                                             |
| `ol,ul`   | Ordered or unordered list                                              |
| `li`      | List item                                                              |
| `a`       | Anchor the text to a hyperlink                                         |
| `img`     | Graphical image reference                                              |
| `dialog`  | Interactive component such as a confirmation                           |
| `form`    | A collection of user input                                             |
| `input`   | User input field                                                       |
| `audio`   | Audio content                                                          |
| `video`   | Video content                                                          |
| `svg`     | Scalable vector graphic content                                        |
| `iframe`  | Inline frame of another HTML page                                      |

### Comments

You can include comments in your HTML files by starting the comment with `<!--` and ending it with `-->`. Any text withing a comment block will be completely ignored when the browser renders it.

```html
<!-- commented text -->
```

### Special characters

HTML uses several reserved characters for defining its file format. If you want to use those characters in your content then you need to escape them using the `entity` syntax. For example, to display a less than symbol (`<`) you would instead use the less than entity (`&lt;`). You can also use the entity syntax to represent any unicode character.

| Character | Entity      |
| --------- | ----------- |
| &amp;     | `&amp;`     |
| <         | `&lt;`      |
| >         | `&gt;`      |
| "         | `&quot;`    |
| '         | `&apos;`    |
| &#128512; | `&#128512;` |
