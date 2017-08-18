# Vim Timestamp
A filetype plugin for timestamping .vim files. 

## Installation
[Pathogen](https://github.com/tpope/vim-pathogen)
```bash
cd ~/.vim/bundle
git clone https://github.com/sgolitsynskiy/vim-timestamp.git
```
## Usage
To add a new timestamp, execute the :TimestampInsert command.
To update an existing timestamp:
* save the file (:write command), or
* execute the :TimestampUpdate command

## Optional Configuration
Suggested mappings to add to your .vimrc:
```vimscript
nnoremap <leader>ti :TimestampInsert<CR>
nnoremap <leader>tu :TimestampUpdate<CR>
```
You may also override the timestamp format by specifyiing these own global variables:
```vimscript
g:timestamp_prefix
g:timestamp_format
g:timestamp_regex
```
Keep in mind that whereas specifying your own prefix (e.g., Last Updated vs. Modified vs. anything else...) is easy, changing the timestamp [format](http://www.manpages.info/linux/strftime.3.html) requires making corresponding edits to the regex variable. 

For example, the current format is `%Y %b %d %X %Z` which renders as `" Last Updated: 2001 May 25 06:00:00 AM PDT`
The corresponding regex is: `'\d\{4\} \a\{3\} \d\{2\} \d\{2\}:\d\{2\}:\d\{2\} [AP]M \a\+'` (note the single quotes and the escapes). 
If you wanted to remove the timezone, you would remove `%Z` from your format variable AND the trailing ` \a\+` from your regex variable. 


## Credits 
Inspired in part by a [more general plugin](http://www.vim.org/scripts/script.php?script_id=923) by [Gautam Iyer](http://www.math.cmu.edu/~gautam/sj)

## Licence
[MIT](https://github.com/sgolitsynskiy/dotfiles/blob/master/LICENSE)
