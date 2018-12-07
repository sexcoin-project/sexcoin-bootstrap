# Sexcoin-Bootstrap

[**Bootstrap files for quick blockchain synchronization**](https://github.com/sexcoin-project/sexcoin-bootstrap/releases)

:point_right: _don't download the source zips...they only contain this README_

**bootstrap.dat** allows a new Sexcoin client (not synced) to rapidly import the initial blocks from a local file instead of slowly downloading blocks from random peers. This significantly reduces the time it takes to get a client synced with the current blockchain.

Simply having bootstrap.dat in Sexcoin's expected data directory will make your initial block sync much faster. The import process can be even faster if you use the *-dbcache=1024* command line parameter which uses an additional 1GB of RAM for the database index cache. Sexcoin v0.10.4.0+ with SSE2 PoW validation can make import even faster if you have SSD drives.

## Overview 
Regardless of your operating system use the following steps to make use of the bootstrap.dat file:

1. Download bootstrap.dat.gz OR bootstrap.dat.zip from github or mirrors.
2. Verify the integrity of the compressed bootstrap.dat file with the checksums.
3. Decompress to obtain bootstrap.dat.
4. Put it into the Sexcoin datadir.  This is the same folder that contains wallet.dat and the blocks folder.
5. Delete bootstrap.dat.old when syncing is finished if you wish to recover some storage space.

## Download bootstrap.dat
You can download bootstrap.dat from sexcoin-project's bootstrap github.
- bootstrap.dat was last built on 2018-12-07.

## Verify integrity
#### bootstrap.dat.gz
 * MD5 : eb092ded7e9c5ad3cd4b2fc28c7e6331
 * SHA1: e5dda169ffde42687af759983d0e47833f2aeec0
 * SHA256: ed10aec5e90d05a500480219ab55308d12e16d4ff58a3f14d63f6b8aa1eb1570
 #### bootstrap.dat.zip
 * MD5 : 9440b6bb2e1e565917863b31701e6911
 * SHA1: 1226e9437d5c1a6183a84d3f1d98c9a44bf38f5c
 * SHA256: 3f34dd125553ff1b0408d0515f95b483a7fb1014814446169f2ec852d284ba45

## Extract bootstrap.dat 
* Linux: <code>gunzip bootstrap.dat.gz</code>
* Mac: You can obtain zip from MacPorts or http://macpkg.sourceforge.net/.
* Windows: [http://www.7-zip.org/](7Zip) is a free utility that can decompress.zip or .gz files.

## Copy bootstrap.dat to data directory
Copy '''bootstrap.dat''' to your data directory. After Sexcoin has used bootstrap.dat, the file will be renamed to bootstrap.dat.old; at this point you can choose to delete it or keep it.

- Linux: Sexcoin's data directory is located in <code>~/.sexcoin/</code> by default. You can run <code>ls -a</code> to see directories that start with a dot.
You can also search for the directory with the following command: <code>find / -name wallet.dat -print 2>/dev/null</code>

- Mac: Sexcoin's data directory should be located in <code>~/Library/Application Support/Sexcoin/</code>.

- Windows: Go to <code>Start>Run</code> (or press <code>WinKey+R</code>) and run: <code>explorer %APPDATA%\Sexcoin</code>
Sexcoin's data directory will open. "AppData" and "Application Data" are hidden by default in Windows.

