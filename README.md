wflz
====

Compress / Decompress code for files with signature WFLZ

Originally from http://wflz.googlecode.com/svn/trunk/

All source is licensed under the WTFPL (sam.zoy.org/wtfpl/).

Random Notes:
-------------

* Compress favors matches further away than CompressFast, this reduces the chances of LHS on PPC, but with a large max match distance this probably slows things down a bit since matches may be out of cache.
* Low max match distances can actually make Compress()'s compression ratio worse than CompressFast().
* If you're after compression ratio: if max dist are the same for Compress and CompressFast, CompressFast will never achieve a better ratio.
* Compression depends on unaligned reads and writes. If this is a problem lemme know! Shouldn't be too hard to fix -- I just don't need to compress on platforms that care (yet...).
