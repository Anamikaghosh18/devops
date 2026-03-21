# 🐧 Basic Linux Commands

## 1. Directory Navigation

```bash
pwd        # Show current directory
ls         # List files
ls -l      # Detailed list
ls -a      # Show hidden files
cd dir     # Move into directory
cd ..      # Go one level up
cd ~       # Go to home directory
```

## 2. File and Directory Mangement 
```bash
touch file.txt        # Create file
mkdir folder          # Create directory

rm file.txt           # Delete file
rm -r folder          # Delete directory
rm -rf folder         # Force delete 


mv file.txt folder/   # Move file
mv old.txt new.txt    # Rename file

cp file.txt copy.txt
cp -r folder newfolder
```
## 3. File Viewing and Editing 
```bash
cat file.txt      # Show full file
less file.txt     # Scrollable view
head file.txt     # First 10 lines
tail file.txt     # Last 10 lines

nano file.txt     # Easy editor
vim file.txt      # Advanced editor

echo "Hello" > file.txt     # Overwrite
echo "Hello" >> file.txt    # Append
```

## 4. Searhing and Filtering
```bash
grep "text" file.txt        # Search text
find . -name "file.txt"     # Find file

wc file.txt     # Lines, words, characters

```

## 5. Links 
```bash 
ln -s /path/to/source linkname # softlink 
ln sourcefile linkname # hardlink

```

## 6. Redirection and pipes 
```bash 
command > file        # Output to file
command >> file       # Append output
command1 | command2   # Pipe output
```

## 7. Sorting and comaparing
```bash
sort file.txt
diff file1 file2 
cut -b 1 file.txt
```



