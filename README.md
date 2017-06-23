# Sexcoin-Bootstrap
**Bootstrap files for quick blockchain synchronization**

**bootstrap.dat** allows a new Sexcoin client (not synced) to rapidly import the initial blocks from a local file instead of slowly downloading blocks from random peers. This significantly reduces the time it takes to get a client synced with the current blockchain.

Simply having bootstrap.dat in Sexcoin's expected data directory will make your initial block sync much faster. The import process can be even faster if you use the *-dbcache=1000* command line parameter which uses an additional 1GB of RAM for the database index cache. Sexcoin v0.10.4.0+ with SSE2 PoW validation can make import even faster if you have SSD drives.

## Overview 
Regardless of your operating system use the following steps to make use of the bootstrap.dat file:

1. Download bootstrap.dat.gz OR bootstrap.dat.zip from github or mirrors.
2. Verify the integrity of bootstrap.dat.gz with the checksums.
3. Decompress to obtain bootstrap.dat.
4. Put it into the Sexcoin datadir.  This is the same folder that contains wallet.dat and the blocks folder.
5. Delete bootstrap.dat.old when syncing is finished to recover some storage space.

## Download bootstrap.dat
You can download bootstrap.dat from sexcoin-project's bootstrap github.
- bootstrap.dat was last built on 2017-06-22.

## Verify integrity
#### bootstrap.dat.gz
 * MD5 : 3bf1159de9f0af83649c268432cf896d
 * SHA1: e4c8af686ac99cf7d4e5102f87e37637373fe5b8
 * SHA256: 0c95fa9c12b0961b887baf4ec9647cd45dc97a742f9354d1aad563491ba15249
 #### bootstrap.dat.zip
 * MD5 : 6d295030162b1094a6e9dcd6f2dd2dd4
 * SHA1: 3420f5c64370ed545c77c5756b008455819c1588
 * SHA256: eb8a01dc15cc163ada11fade48b143d4dfabc54e135dd100aa373789d9d1ab52

## Extract bootstrap.dat 
* Linux: <code>gunzip bootstrap.dat.gz</code>
* Mac: You can obtain zip from MacPorts or http://macpkg.sourceforge.net/.
* Windows: [http://www.7-zip.org/](7Zip) is a free utility that can decompress.zip or .gz files.

## Copy bootstrap.dat to data directory
Copy '''bootstrap.dat''' to your data directory. After Sexcoin has used bootstrap.dat, the file will be renamed to bootstrap.dat.old; at this point you can choose to delete it or keep it.

- Linux: Sexcoin's data directory is located in <code>~/.litecoin/</code> by default. You can run <code>ls -a</code> to see directories that start with a dot.
You can also search for the directory with the following command: <code>find / -name wallet.dat -print 2>/dev/null</code>

- Mac: Sexcoin's data directory should be located in <code>~/Library/Application Support/Sexcoin/</code>.

- Windows: Go to <code>Start>Run</code> (or press <code>WinKey+R</code>) and run: <code>explorer %APPDATA%\Sexcoin</code>
Sexcoin's [[#Data directory chart|data directory]] will open. "AppData" and "Application Data" are hidden by default in Windows.

