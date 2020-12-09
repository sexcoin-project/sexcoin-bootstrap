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
- bootstrap.dat was last built on 2020-12-08.

## Verify integrity
#### bootstrap.dat
* md5:    64b9d52c8b8e64972d71c7a90f49a579  -
* sha1:   d119c77a474575f5196b05d453e5f3ca5ebb5a0b  -
* sha256: 142f359cafe8adcee1e942464d65e8bae64042719f325214713215a2e970c62e  -

#### bootstrap.dat.gz
* md5:    bd982ea50050e45172a48a98691624ff  -
* sha1:   2f1bf61c1424c6c9573c9194bc551bf315134a2b  -
* sha256: 105d6d9b1a88ee743936a38307399f0f53ef2b87442c863a644896a827f7a0e1  -

#### bootstrap.dat.zip
* md5:    1436e1acbd89510f9335281beb8ee781  -
* sha1:   7c1ad16ca7adbfcdd3b093b8529c2183b62027a8  -
* sha256: 2ada3376c4fdab93b51b1c4e837e8a15a0eac1a0edc4a45f6123818c34c7722e  -


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

