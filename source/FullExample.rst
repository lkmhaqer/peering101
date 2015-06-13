============
Full Example
============

An example of a fully worked through configuration.

Cisco IOS
---------

For Cisco we can use aggregation (-A) flag to make this prefix-filter
more compact:

     user@host:~>bgpq3 -Al eltel AS20597
     no ip prefix-list eltel
     ip prefix-list eltel permit 81.9.0.0/20
     ip prefix-list eltel permit 81.9.32.0/20
     ip prefix-list eltel permit 81.9.96.0/20
     ip prefix-list eltel permit 81.222.128.0/20
     ip prefix-list eltel permit 81.222.192.0/18
     ip prefix-list eltel permit 85.249.8.0/21
     ip prefix-list eltel permit 85.249.224.0/19
     ip prefix-list eltel permit 89.112.0.0/18 ge 19 le 19
     ip prefix-list eltel permit 89.112.4.0/22
     ip prefix-list eltel permit 89.112.64.0/19
     ip prefix-list eltel permit 217.170.64.0/19 ge 20 le 20

Cisco IOS-XR
------------
Generating named IOS-XR prefix-filter for `AS20597`:

     user@host:~>bgpq3 -Xl eltel AS20597
     no prefix-set eltel
     prefix-set eltel
      81.9.0.0/20,
      81.9.32.0/20,
      81.9.96.0/20,
      81.222.128.0/20,
      81.222.192.0/18,
      85.249.8.0/21,
      85.249.224.0/19,
      89.112.0.0/17,
      217.170.64.0/19
     end-set

Juniper JUNOS
-------------

Generating named Juniper prefix-filter for `AS20597`:

     user@host:~>bgpq3 -Jl eltel AS20597
     policy-options {
     replace:
      prefix-list eltel {
         81.9.0.0/20;
         81.9.32.0/20;
         81.9.96.0/20;
         81.222.128.0/20;
         81.222.192.0/18;
         85.249.8.0/21;
         85.249.224.0/19;
         89.112.0.0/19;
         89.112.4.0/22;
         89.112.32.0/19;
         89.112.64.0/19;
         217.170.64.0/20;
         217.170.80.0/20;
      }
     }

Brocade IronWare
----------------

Arista EOS
----------

and more...
