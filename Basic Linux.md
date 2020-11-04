### Deleting files 😸
* `rm file` removing file
* `rm -r dir` removing the directory and all the content
* `rm -f file` force removing file without prompting 
* `rm s*` removing file and directory with the first character s
* `rm .*` removing the file and folder with the first character is . 

### Copying files 😸
* `cp source_file directory_file` copying 1 file into dest directory
* `cp src_file1 src_fileN dest_dir` copying more file into dest directory
* `cp -i` copying with interactive mode
* `cp -r source_directory destination` copying dir/file to dest dir, when dest dir not exist then create

### Moving files and renaming files 😸
* `mv` this command can use for renaming and moving file/dir
* `mv src dest`
* `mv -i src dest`

### Compress files and creating archives 😸
**tar**
* `tar [-] c|x|t tarfile [pattern]`
* `tar cf test.tar tes1` example
* `tar xvf test.tar` example
* `tar zcf test.tgz/tar.gz tes1` example

**tar options**
* `c` opt for create tar
* `x` opt for extart tar
* `t` opt for read content tar
* `v` opt for verbose (diplaying details about name file is process)
* `z` opt for using compression
* `f file` use the file

**compressing file to save space**
* `gzip data` example (output file data.gz)
* `gzip` for compressing data
* `gunzip` for uncompressing data
* `gzcat/zcat` for read the content trought the termainal/cli or internet says another way for uncompressing data

### Other 😸

**SORT**
* `sort file` to sorting content of file
* `sort -ru -k2 file1` example1

**SORT OPTIONS**
* `-k F` opt for selecting sort by row (F=row/field)
* `-r` ort for reversing sort
* `-u` opt for to take only unique value 

**disk usage**
* `du` estimating file usage
* `du -k` displaying in kilobyte
* `du -h` displaying in human readable

**other**
* `ls s*` showing file/directory with the first character s
* `ls -d s*` showing directory with the first char is .
* `cat file1` to read the content in file

## Wildcards
* `*` matches zero or more char
* `ls fil*` example

* `?` matches exacly one char
* `ls f?le` example

* `[]` a char class
* `ls ca[nt]*` example
* `[!aiueo]*` example
* `[a-g]*` example
* `[3-6]*` example

* `[[:alpha:]]`
* `[[:alnum:]]`
* `[[:digit:]]`
* `[[:lower:]]`
* `[[:space:]]`
* `[[:upper:]]`
* `ls *[[:digit:]]` example

* `\` for match a wildcard char
* `*\? example

## I/O and Redicrection
I/O name | Abbreviaition | File Descriptor
Standartd Input | stdin | 0
Standard Output | stdout | 1
Standart Error | stderr | 2

### Redirection
* `>` redirect stdout to a file = overwrite existing content
* `>>` redirect stdout to a file = append to any existing content
* `<` redirect input from a file to commmand
* `&` used with direction to signal that a file descriptor being used

### The null device
* `> /dev/null/` redirect output to nowhere / passing to null device it / passing and not save the log

* `ls file1 not-here > out` example
* `sort < file1 > out` example
* `ls -l 1> out` example
* `ls >> out`example
* `ls file1 not-here 1> out 2> out.err` example
* `ls file1 not-here 1> out.both 2>&1` example

## Comparing files

* `diff file1 file2` compare two filw
* `3c3 = LineNumFile1-Action-LineNumFile2`
* `Action = (A)dd (C)hange (D)elete`

* `sdiff file1 file2` side-by-side comparison

* `vimdiff file1 file2` Highligth different in vim
vimdiff
* `ctrl+w / w` goto the next window
* `q` quit (close current windows)
* `qa` quit all
* `qa!` force quit all


### Insight 😸
```
1. Perbedaan achiving dengan compressing!
   - Archiving memasukkan data kedalam rar, tar, tgz, dll
   - Compressing sama dengan archiving namun dapat merubah data menjadi lebih  kecil / ringan (compressing data)
```
