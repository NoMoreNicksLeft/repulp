# repulp
Digital re-typesetting the classics.

For many years, I have wanted to be able to collect a few vintage magazine issues in a modern digital format, which plainly seems impossible given the dates of publication. Many of these are pre-ebook, most are pre-computer-era. So I decided to do something about it.

I've fumbled around for quite a long while, even trying to decide what it would mean. I took awhile to warm up to EPUB format, and even once I started to accept its several virtues, it still seemed as if it were far from ideal for periodicals and magazines. I was obsessed with PDF, until I started to write software that produced those files. It is a thoroughly nasty thing best left undiscussed, but let it suffice to say this: PDFs are horrid to try to read on mobile devices. Some of that isn't the format's fault, but the original print issues' own. 

I started asking myself, what would it mean to "digitally remaster" a print magazine into the EPUB format, and what would make that an authentic reproduction? This project is an attempt to understand that question and come up with a sensible answer.

The basic requirements as I see them are

* All content must be present, no matter how trivial or inconsequential
* Stylistic choices must also be preserved, including typefaces, clip art, graphical placement, and so on
* Advertisements, while unimportant to many, are no exception to the above rules

… but the following stuff is just awful and needs to be dumped

* (Forced) two column layouts
* Page numbering and non-reflowable text content
* "Continued on page 118"s

There are many challenges. Finding pristine scans of original artwork and photographs, many typefaces from the print era have either not yet been digitized or have been digitized insufficiently, many issues will require dozens of hours of vectorization of trivial graphical elements, and the importance and extent of semantic markup remains unexplored. If anyone wants to help, there are plenty of tasks that don't require coding or art skill, but I'm content that this may be a one man job even if I could use the help.

## Unanswered questions

### What is the minimum resolution for book covers (and video game box art) present in some advertisements?

Analog magazine would nearly constantly have ads from Science Fiction Book Club, and these ads could have as many as 30 thumbnail-sized book covers. Additionally many issues would have a dozen or more ads for single titles all featuring the book covers (again, in thumbnail-sized images). With the high-resolution images sometimes weighing in at 1-4mb in size, x45 per issue and all of them JPEG format (and essentially uncompressible in EPUB's zip compression), those file sizes are impractical. We don't need resolutions of 2400h+, and for something that might've only been one inch tall in print it's absurd. Can we get away with a 100px tall png?

### How closely do fonts need to match the original print?

I've already stumbled across many examples, but they're all so irritating. An interior typeface in Analog can be matched perfectly... except that its apostrophe has a flat bottom while the matching font has an angled bottom. 1970s Galaxy covers use Staundel Xenotype J (or a variant) that can be matched perfectly except for the uppercase S (in "Science Fiction"). Can those slight mismatches be ignored?

### How should two page spread interior art be handled?

Ebooks do not have two pages side by side (excepting iPad apps might do this in landscape mode?). The artwork was always meant to be viewed together, whole, and at best it is an inferior viewing experience to see it chopped in halves and shown one after the other. At worst, it is incomprehensible. While text content (usually titles) can be normalized and presented on a single page, artwork should remain intact. Should it shrink to fit on a single page? The orientation doesn't always work for that strategy.

