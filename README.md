# mybible-tools
Command line tools for working with Mybible Android app's module database formats

# dependencies:
sqlite. to install it just run:
```sh
sudo pacman -S sqlite
```

# installation:
just put scripts that are in bin to your PATH:
for example:
```sh
cp bin/* ~/.local/bin/
```
# usage:
first you have to cd into desired directory where you want html files to be generated
```sh
mybible2htmltable -l [DATABASE] # list books from the database
mybible2htmltable -h            # show help message
mybible2htmltable [DATABASE]    # operate on an entire bible
mybible2htmltable [DATABASE] [book] # operate only on [book]
mybible2htmltable [DATABASE] [bookfrom] [bookto] # operate on range
```
DATABASE should be one of MyBible Android application's bible modulewhich does not contain strongs numbers and morphology or other incompatible markup to html.

book should be either book_number or substring from its names (short or long)


# epub creation from output:
requires pandoc
```sh
pandoc -o /path/to/output_file.epub --epub-title-page=false --toc-depth=6 --split-level=2 --metadata=author:'some bible society' --metadata=title:'New Testament Patriarchal Text' --metadata=language:'el' --css=/path/to/style.css *
```

