backitup
========

simple backup script for desktop linux using standard stuff: 
tar, openssl for file encrypt, ssh for copy to remote. 

supports tar listed-incremental mode, but with only level 0 and 1

supports tar --exclude-tag=<tag> with tag MYCACHE.TAG -- put an empty
file called MYCACHE.TAG in any directory you don't want backed up. 
