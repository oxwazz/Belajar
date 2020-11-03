## deleting files
* `rm file` removing file
* `rm -r dir` removing the directory and all the content
* `rm -f file` force removing file without prompting 
* `rm s*` removing file and directory with the first character s
* `rm .*` removing the file and folder with the first character is . 

* `ls s*` showing file/directory with the first character s
* `ls -d s*` showing directory with the first char is .

## copying files
* `cp source_file directory_file` copying 1 file into dest directory
* `cp src_file1 src_fileN dest_dir` copying more file into dest directory
* `cp -i` copying with interactive mode
* `cp -r source_directory destination` copying dir/file to dest dir, when dest dir not exist then create

## moving files and renaming files
* `mv` this command can use for renaming and moving file/dir
* `mv src dest`
* `mv -i src dest`

* `cat file1` to read the content in file

## compress files and creating archives
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

## other

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

```
1
perbedaan achiving dengan compressing
archiving memasukkan data kedalam rar, tar, tgz, dll
compressing sama dengan archiving namun dapat merubah data menjadi lebih  kecil / ringan (compressing data)
```
