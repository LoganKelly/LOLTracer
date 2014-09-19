#LOLTracer

##Setup

The following LOLCODE was written and executed using lci v0.10.5. It uses v1.3 of the specification as implemented in that version of lci. Compatibility with other LOLCODE compilers and interpreters is not guaranteed (nor is it very likely).

Download and install lci here:

[https://github.com/justinmeza/lci/releases/tag/v0.10.5](https://github.com/justinmeza/lci/releases/tag/v0.10.5)
 
Since v1.3 of LOLCODE is not official, (the latest version on lolcode.org as of this writing is 1.2), it is recommended that you check the following website, or the lci google group, for the ways in which v1.3 differs from v1.2:

[https://web.archive.org/web/20120420194728/http://lolcode.com/proposals/1.3/bukkit2](https://web.archive.org/web/20120420194728/http://lolcode.com/proposals/1.3/bukkit2)

##Usage

For Windows or Linux, run the following from the command line:

`lci.exe LOLTracer.lol > LOLrender.ppm`

Expect several hours render time for the image to complete with default settings. On my home desktop with a Quad Core 2.4 Ghz CPU it took approximately 40 hours to complete. If you would like faster results, I recommend changing the number of rays used from 64 to a lower number. However since the pixel color is accumulated
over many samples, the resulting image will be darker. If you lower the number of rays, I also recommend increasing the default colors for the ground and sky by a proportional amount.

##Background

The LOLtracer was written, on a dare, to see if it would be possible to implement a raytracer in LOLCODE. I am happy to report that it is VERY MUCH possible, although not terribly fast. The LOLtracer also attempts to be as faithful as possible to the implementation of Andrew Kensler's business card raytracer:

[http://fabiensanglard.net/rayTracing_back_of_business_card/](http://fabiensanglard.net/rayTracing_back_of_business_card/)

Additional information about his raytracer can be
found here:

[https://news.ycombinator.com/item?id=6425965](https://news.ycombinator.com/item?id=6425965)

And a python version of his raytracer by Ivo van der Wijk
can also be found here:

[http://vanderwijk.info/blog/business-card-raytracer-in-python/](http://vanderwijk.info/blog/business-card-raytracer-in-python/)

Most of the challenge in faithfully reproducing
Kensler's raytracer in LOLCODE lay in finding ways
to have access to the same standard library of functions
available in C that are used in the business card raytracer.
v1.3 of LOLCODE does not have bindings for C standard lib,
so I was forced to re-write many common routines
in LOLCODE as a substitute. These included sqrt(), rand(),
ceil(), and pow(). Originally I tried to recreate bitshift
left and bitwise and as well, but those operations proved
far too slow even for LOLCODE. Even though they are
no longer called, those functions are left in for posterity.

##Author

Logan Kelly (logan.kelly@gmail.com)

##Date

Sept. 17th, 2014
