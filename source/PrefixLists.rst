======================================
Generating a Prefix List for your peer
======================================

Be sure to explain difference between aut-num and as-set.

Also, be sure to explain what these things are to someone from the ARIN region. Don't go deep, just explain a simple example record from RIPE or APNIC. Then work it through into how an inverse lookup works to find the prefixes.

HOWEVER, don't bore them, somewhere near the top show how to use bgpq3.


With prefixes being added and removed constantly on the Internet, how do you dynamically keep track of who should be allowed to announce what to you? IRR fills this space by providing a database of information formally setting what origin ASNs and prefixes match up.

The system is built on "objects" of RPSL which vary from one IRR DB provider to another. The main objects, and what you need to get started, are "mntner", "route", "aut-num" and "as-set." The "mntner" object acts as an authority to which all your other objects point. "route" and "route6" objects are for prefixes, pointing towards an origin ASN. The "as-set" and "aut-num" represent either a single ASN, or a group of ASNs respectively. For an ASN that has all these in place, and upstream or peer can now get all relevant information with just a few simple queries of IRR.

In the interest of getting all the prefixes that your peer should be announcing, you can simply ask them if they prefer filtering on their ASN, or if they have an as-set. If they want just a single ASN, every prefix they want to announce will have to have a route or route6 object with matching origin ASN. An as-set will allow them to place their ASN, along with their customer ASNs or as-sets. We can query IRR for all the prefixes under a given ASN, and also return every asn in an as-set, to a given depth. With this, and a handy utility called bgpq3, we generate a prefix list for a peer.

whois inverse queries:

all route objects under an ASN:
whois -h irr.dbhost.net -i origin AS64496 

whois -i mnt-by MAINT-AS64496




Sources:

https://www.nanog.org/meetings/nanog51/presentations/Sunday/NANOG51.Talk34.NANOG51%20IRR%20Tutorial.pdf
