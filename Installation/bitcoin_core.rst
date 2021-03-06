Bitcoin Core with ``addrindex`` patch
-------------------------------------------------------

Bitcoin Core is used by Counterparty to interact with the Bitcoin blockchain.
However, vanilla Bitcoin Core is insufficient---instead, a version patched to
enable an 'address index' is required.


Download
========
https://github.com/btcdrak/bitcoin/releases


Installation
============
*Installer* *TODO*


Configuration
====================

On Windows
-----------

Type Windows Key-R and enter ``cmd.exe`` to open a Windows command prompt. Type the following::

    cd %APPDATA%\Bitcoin
    notepad bitcoin.conf  

Say 'Yes' to when Notepad asks if you want to create a new file, then paste in the text below::

    rpcuser=bitcoinrpc
    rpcpassword=
    server=1
    daemon=1
    rpcthreads=1000
    rpctimeout=300
    txindex=1
    addrindex=1

**NOTE**:

    Choose a secure password!


Reindex
=======

If this is not the first time you are running Bitcoin Core on this computer,
you'll probably need to launch ``bitcoind`` as follows:

    bitcoind --reindex

    
This will start up bitcoin to do a one-time reindexing of the blockchain on
disk.
