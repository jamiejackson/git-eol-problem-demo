# eol-test

Figure out cross-platform EOL strategy.


----

Notes on creation:

```
$ file test_files/created_before_gitattributes/*
test_files/created_before_gitattributes/crlf_authored_before_gitattributes.bat: ASCII text, with CRLF line terminators
test_files/created_before_gitattributes/crlf_authored_before_gitattributes.sh:  ASCII text, with CRLF line terminators
test_files/created_before_gitattributes/crlf_authored_before_gitattributes.txt: ASCII text, with CRLF line terminators
test_files/created_before_gitattributes/lf_authored_before_gitattributes.bat:   ASCII text
test_files/created_before_gitattributes/lf_authored_before_gitattributes.sh:    ASCII text
test_files/created_before_gitattributes/lf_authored_before_gitattributes.txt:   ASCII text
test_files/created_before_gitattributes/mixed_eol.txt:                          ASCII text, with CRLF, LF line terminators
```

After `.gitattributes`, adding new files:

```
ICF2008571:eol-test jjackson$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   test_files/created_before_gitattributes/crlf_authored_before_gitattributes.bat
        modified:   test_files/created_before_gitattributes/crlf_authored_before_gitattributes.sh
        modified:   test_files/created_before_gitattributes/crlf_authored_before_gitattributes.txt
        modified:   test_files/created_before_gitattributes/mixed_eol.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        test_files/created_after_gitattributes/

no changes added to commit (use "git add" and/or "git commit -a")
ICF2008571:eol-test jjackson$ git add .
warning: CRLF will be replaced by LF in test_files/created_before_gitattributes/crlf_authored_before_gitattributes.sh.
The file will have its original line endings in your working directory
warning: CRLF will be replaced by LF in test_files/created_before_gitattributes/crlf_authored_before_gitattributes.txt.
The file will have its original line endings in your working directory
warning: CRLF will be replaced by LF in test_files/created_before_gitattributes/mixed_eol.txt.
The file will have its original line endings in your working directory
warning: CRLF will be replaced by LF in test_files/created_after_gitattributes/crlf_authored_after_gitattributes.sh.
The file will have its original line endings in your working directory
warning: CRLF will be replaced by LF in test_files/created_after_gitattributes/crlf_authored_after_gitattributes.txt.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in test_files/created_after_gitattributes/lf_authored_after_gitattributes.bat.
The file will have its original line endings in your working directory
warning: CRLF will be replaced by LF in test_files/created_after_gitattributes/mixed_eol.txt.
The file will have its original line endings in your working directory
ICF2008571:eol-test jjackson$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   test_files/created_after_gitattributes/crlf_authored_after_gitattributes.bat
        new file:   test_files/created_after_gitattributes/crlf_authored_after_gitattributes.sh
        new file:   test_files/created_after_gitattributes/crlf_authored_after_gitattributes.txt
        new file:   test_files/created_after_gitattributes/lf_authored_after_gitattributes.bat
        new file:   test_files/created_after_gitattributes/lf_authored_after_gitattributes.sh
        new file:   test_files/created_after_gitattributes/lf_authored_after_gitattributes.txt
        new file:   test_files/created_after_gitattributes/mixed_eol.txt
        modified:   test_files/created_before_gitattributes/crlf_authored_before_gitattributes.bat
        modified:   test_files/created_before_gitattributes/crlf_authored_before_gitattributes.sh
        modified:   test_files/created_before_gitattributes/crlf_authored_before_gitattributes.txt
        modified:   test_files/created_before_gitattributes/mixed_eol.txt

ICF2008571:eol-test jjackson$ git commit -m 'add files after .gitattributes'
[master 3eec70a] add files after .gitattributes
 11 files changed, 84 insertions(+), 26 deletions(-)
 create mode 100644 test_files/created_after_gitattributes/crlf_authored_after_gitattributes.bat
 create mode 100644 test_files/created_after_gitattributes/crlf_authored_after_gitattributes.sh
 create mode 100644 test_files/created_after_gitattributes/crlf_authored_after_gitattributes.txt
 create mode 100644 test_files/created_after_gitattributes/lf_authored_after_gitattributes.bat
 create mode 100644 test_files/created_after_gitattributes/lf_authored_after_gitattributes.sh
 create mode 100644 test_files/created_after_gitattributes/lf_authored_after_gitattributes.txt
 create mode 100644 test_files/created_after_gitattributes/mixed_eol.txt
 
ICF2008571:eol-test jjackson$ file test_files/**/*
test_files/created_after_gitattributes/crlf_authored_after_gitattributes.bat:   ASCII text, with CRLF line terminators
test_files/created_after_gitattributes/crlf_authored_after_gitattributes.sh:    ASCII text, with CRLF line terminators
test_files/created_after_gitattributes/crlf_authored_after_gitattributes.txt:   ASCII text, with CRLF line terminators
test_files/created_after_gitattributes/lf_authored_after_gitattributes.bat:     ASCII text
test_files/created_after_gitattributes/lf_authored_after_gitattributes.sh:      ASCII text
test_files/created_after_gitattributes/lf_authored_after_gitattributes.txt:     ASCII text
test_files/created_after_gitattributes/mixed_eol.txt:                           ASCII text, with CRLF, LF line terminators
test_files/created_before_gitattributes/crlf_authored_before_gitattributes.bat: ASCII text, with CRLF line terminators
test_files/created_before_gitattributes/crlf_authored_before_gitattributes.sh:  ASCII text, with CRLF line terminators
test_files/created_before_gitattributes/crlf_authored_before_gitattributes.txt: ASCII text, with CRLF line terminators
test_files/created_before_gitattributes/lf_authored_before_gitattributes.bat:   ASCII text
test_files/created_before_gitattributes/lf_authored_before_gitattributes.sh:    ASCII text
test_files/created_before_gitattributes/lf_authored_before_gitattributes.txt:   ASCII text
test_files/created_before_gitattributes/mixed_eol.txt:                          ASCII text, with CRLF, LF line terminators
```

fresh clone

```
ICF2008571:eclipse-workspace jjackson$ git clone https://gitlab.e3si.icfcloud.com/hudx/eol-test.git eol-test-fresh
Cloning into 'eol-test-fresh'...
remote: Enumerating objects: 31, done.
remote: Counting objects: 100% (31/31), done.
remote: Compressing objects: 100% (28/28), done.
remote: Total 31 (delta 10), reused 0 (delta 0)
Unpacking objects: 100% (31/31), done.
ICF2008571:eclipse-workspace jjackson$ cd eol-test-fresh/
ICF2008571:eol-test-fresh jjackson$ file test_files/**/*
test_files/created_after_gitattributes/crlf_authored_after_gitattributes.bat:   ASCII text, with CRLF line terminators
test_files/created_after_gitattributes/crlf_authored_after_gitattributes.sh:    ASCII text
test_files/created_after_gitattributes/crlf_authored_after_gitattributes.txt:   ASCII text
test_files/created_after_gitattributes/lf_authored_after_gitattributes.bat:     ASCII text, with CRLF line terminators
test_files/created_after_gitattributes/lf_authored_after_gitattributes.sh:      ASCII text
test_files/created_after_gitattributes/lf_authored_after_gitattributes.txt:     ASCII text
test_files/created_after_gitattributes/mixed_eol.txt:                           ASCII text
test_files/created_before_gitattributes/crlf_authored_before_gitattributes.bat: ASCII text, with CRLF line terminators
test_files/created_before_gitattributes/crlf_authored_before_gitattributes.sh:  ASCII text
test_files/created_before_gitattributes/crlf_authored_before_gitattributes.txt: ASCII text
test_files/created_before_gitattributes/lf_authored_before_gitattributes.bat:   ASCII text, with CRLF line terminators
test_files/created_before_gitattributes/lf_authored_before_gitattributes.sh:    ASCII text
test_files/created_before_gitattributes/lf_authored_before_gitattributes.txt:   ASCII text
test_files/created_before_gitattributes/mixed_eol.txt:                          ASCII text
```