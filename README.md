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
- bootstrap.dat was last built on 2023-03-29.

## Verify integrity
#### bootstrap.dat

* md5:    137b4f4eb02179647d64a93ec7a6b457  -
* sha1:   e48e036b3510e6e6b83d4d47b18234f3a18b1157  -
* sha256: 9c0f3aeacae55c9675c969e6df95dbf98e0e21492cadbc648600237f7d5b5846  -

#### bootstrap.dat.gz

* md5:    4732631b3f20fa2bc438da326f97ab43  -
* sha1:   8237c46aef44642fc5815872910ea8ff40062c72  -
* sha256: 9e2ef62cb37f104e5ff106dee365313f950ba2ed7614902c1e04d81b42f4085a  -

#### bootstrap.dat.zip

* md5:    8a413f0028abf01241eafa4009a95c67  -
* sha1:   c7548ea4d407c606cf5d8ae28115f7bafa907dcd  -
* sha256: d62cc12ec5ed4f1fd56a53f84b30ee9fa67769b30b3c3108791204c0b50a6a33  -


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

