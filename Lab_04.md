* Sorting:
    * `sort file.txt` - Sort the contents of a file.
    * `sort -r file.txt` - Sort in reverse order.
    * `sort -n file.txt` - Sort numerically.
    * `sort -u file.txt` - Sort and remove duplicates.
    * `sort -k2 file.txt` - Sort by the second column.

* Archiving & Compression:
    * `tar -cf archive.tar file1 file2` - Create a new archive file.
    * `tar -rf archive.tar file3` - Append a file to an archive.
    * `tar -tf archive.tar` - List the contents of an archive.
    * `tar -xf archive.tar` - Extract an archive.
    * `gzip archive.tar` - Compress an archive.
    * `gzip -d archive.tar.gz` - Decompress an archive.

* Wildcards:
    * `*` - Matches any number of characters.
    * `?` - Matches a single character.
    * `[]` - Matches any character within the brackets.
    * `[^]` - Matches any character not within the brackets.

* Differences:
    * `diff file1 file2` - Show the differences between two files.
    * `diff -u file1 file2` - Show differences with unified context.
    * `diff -i file1 file2` - Ignore case differences.