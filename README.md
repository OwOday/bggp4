A friend told me a couple months ago that PDFs original spec was super crazy and Turing complete. It's still Turing complete kinda but I started trying to read about older PDF specs. Since I can barely read I was thankful this challenge came along to get me to learn a little bit about it. I gotta say, the older PDF specs are pretty cool in a fucked up kinda way. It was interesting to learn how much of the spec acrobat simply didnt care was missing. Thanks for hosting the challenge again this year!

The official submission lies in "displays4interminal", instructions in entry below. There also exists "displays4inpage" which is a not-fully-golfed version that displays 4 on the page instead of cmd (much bigger due to pdf spec)

A couple loopholes I used:
> searches whole filesystem for the file to save characters and avoid the problem where pdfs Launch drops you into system32
> copies the file and its whole path into tmp, which saves characters but makes it hard to find

There was a lot of workarounds for weird bugs like calling robocopy in cmd after seemingly needlessly changing directory, some of which make it seem like I didn't use the shortest option in some places, but I couldn't make the alternatives work in any cases I noticed.

The extras folder contains various files I generated/borrowed/made that I either arrived at as a checkpoint or used for inspiration/investigation


---BEGIN BGGP4 ENTRY---

Name or handle: gaycomputers

Contact Info: 

Website, twitter, other online presence: @podling@jorts.horse

Target File Type: pdf

SHA256 Hash: 316a42b34e4266b1f0b8ce90e008f673f67cfc1e2cbd2005bd6eef85b8c19c13

Target Environment (How do we run the file?): Windows 11 (I'm on 25201.1000), Adobe Acrobat 8 Standard (I used https://acrobat.adobe.com/link/track?uri=urn%3Aaaid%3Ascds%3AUS%3A80aa8c58-2951-494e-808a-fb61a6b4aa29 and the serial at https://archive.org/details/acrobat-8)

Any additional info?: In order to solve not being able to open cmd in a local path (and to golf better), the payload searches your entire computer for files named exactly "4". It also preserves the directory structure (to golf better) when it copies it into %TMP%. As a result the exploit takes a very very long time to run, if you are just testing it I recommend replacing "robocopy ./" with "robocopy *PATH_TO_DIR_CONTAINING_PDF*". The file should copy the itself then echo 4 to the terminal. Since I cant get a working directory or local directory in pdf it is essential that the file be named "4" exactly. Also, you need to accept a prompt for the cmd to kick off, digging for an old enough copy that it is still able to open a shell on Windows 11 was hard enough so I didn't bother finding one without the prompt.

Link to PoC video, screenshot, or console output, if any: https://github.com/gaycomputers/bggp4/blob/main/photos/complete.png (4 is in bottom left)

Link to writeup, if any: https://github.com/gaycomputers/bggp4

File contents (base64 encoded please): JVBERi0xLgowIDAgb2JqPDwvUGFnZXM+PmVuZG9iagp0cmFpbGVyPDwvUm9vdDw8L1BhZ2VzPDw+Pi9PcGVuQWN0aW9uPDwvUy9MYXVuY2gvV2luPDwvRiAoY21kLmV4ZSkvUCAoL0sgY2QgLi4vLi4gJnJvYm9jb3B5IC4vICVUTVAlIC9zIC9JRiAiNCIgJmVjaG8gNCk+Pj4+Pj4+Pg==

---END BGGP4 ENTRY---
