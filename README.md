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
- bootstrap.dat was last built on 2017-07-01.

## Verify integrity
#### bootstrap.dat.gz
 * MD5 : e4c2c3c5e41ca968932b06f9c7967a66
 * SHA1: 306e16e6a5d6f3a5bd7384f25dec0d1da12f1583
 * SHA256: ea680573dea3ccc195877e825885c892ed76e3561a75de5d5c6fbefd4d814ec1
 #### bootstrap.dat.zip
 * MD5 : bee6cb3497abc96e40c4dbe28e8b1cbc
 * SHA1: fd2efa122310bd7e042b68e71b0ef4feb022d26f
 * SHA256: c922aa523587f80b34069e66906dca26128db6e1904223bf3831e9e7c51506e4

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

