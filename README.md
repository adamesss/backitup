backitup
========

simple backup script for desktop linux using standard stuff: 
tar, openssl for file encrypt, ssh for copy to remote. 

supports tar listed-incremental mode, but with only level 0 and 1

supports tar --exclude-tag=<tag> with tag MYCACHE.TAG -- put an empty
file called MYCACHE.TAG in any directory you don't want backed up. 

to restore, just decrypt the file(s) by hand if required: `openssl des -d -in archive.n.tgz.des -out archive.n.tgz`,
enter the encryption key when prompted. then untar normally, starting with level 0 then level 1. no
special tar options are needed on restore.

### why yet another backup script?

the backup system i use on my servers is based on "dump" and doesn't do 
incrementals at the file/directory level (only at the filesystem level).
for my desktop pc, i don't need a backup of the whole filesystem,
really only my home dir and maybe a couple dirs with config stuff.

also, the scp to remote and encryption options are different than what 
i normally need on my private server network. 

and the ubuntu backup program sucks (well, maybe it doesn't, but 
it's non-standard at best, apparently only does full restores, only 
supports gpg, and i wouldn't know how to restore on a non-ubuntu 
machine without some effort)
