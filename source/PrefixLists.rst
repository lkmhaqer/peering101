======================================
Generating a Prefix List for your peer
======================================

Be sure to explain difference between aut-num and as-set.

Also, be sure to explain what these things are to someone from the ARIN region. Don't go deep, just explain a simple example record from RIPE or APNIC. Then work it through into how an inverse lookup works to find the prefixes.

HOWEVER, don't bore them, somewhere near the top show how to use bgpq3.


With prefixes being added and removed constantly on the Internet, how do you dynamically keep track of who should be allowed to announce what to you? IRR fills this space by providing a database of information formally setting what origin ASNs and prefixes match up. The system is built on "objects" which vary from one IRR DB provider to another. The main objects, and what you need to get started, are "mntner", "route", "aut-num" and "as-set."
