[Github file size limit changed 6/18/13. Can't push now](http://stackoverflow.com/q/17382375/395857)

The actual limit on GitHub for each file is 100 MiB, not 100 MB.

----------

https://help.github.com/articles/what-is-my-disk-quota/  ([mirror](https://web.archive.org/web/20170329161408/https://help.github.com/articles/what-is-my-disk-quota/)) erroneously claims that they place a strict limit of files exceeding 100 MB in size

The confusion between MB and MiB can be seen when pushing: in the example below, the error message from GitHub server indicates the file is 101 MB whereas git correctly indicates it is 101 MiB:

```
    ~\Documents\GitHub\test123 [master ↑1 +3 ~0 -0 !]> git push
    Counting objects: 3, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 101.03 MiB | 896.00 KiB/s, done.
    Total 3 (delta 1), reused 0 (delta 0)
    remote: Resolving deltas: 100% (1/1), completed with 1 local objects.
    remote: error: GH001: Large files detected. You may want to try Git Large File S
    torage - https://git-lfs.github.com.
    remote: error: Trace: e9206a9cd05c4ff5de79bba9d4caf9df
    remote: error: See http://git.io/iEPt8g for more information.
    remote: error: File 101MB is 101.00 MB; this exceeds GitHub's file size limit of
     100.00 MB
    To https://github.com/Franck-Dernoncourt/test123.git
     ! [remote rejected] master -> master (pre-receive hook declined)
    error: failed to push some refs to 'https://github.com/Franck-Dernoncourt/test12
    3.git'
    ~\Documents\GitHub\test123 [master ↑1 +3 ~0 -0 !]>
```