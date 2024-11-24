## what is shpkg?
it is a cross-distro package manager that uses shell scripts to install packages. you see, packages are complicated, and most people don't make package their software anyways. then we said,
> what if we made packaging fun and easy so it's more accessible and developer-friendly?

and that started shpkg/shpm's journey.

24.11.2024 (us 11.24.2024) - shpkg/shpm was created
## how does it work?
shpkg first searches for the desired package name ending with .sh in the `https://github.com/shpkg/repo` git repository. if it finds a match, it curl-bashes the script. else, it fails.
## what are the requirements for packages?
well, let's see...
- both software installed and the installer script **MUST** be open-source, accessible via a git/mercurial/subversion repository.
- both software installed and the installer script **MUST NOT** contain [any type of malware](https://en.wikipedia.org/wiki/Category:Types_of_malware)
- the so-called "installer" **MUST** install **ONLY** the software and **ITS DEPENDENCIES**. bundleware **IS NOT** allowed.
- the installer **MUST** actually **INSTALL** the package it is connected to. **EMPTY** shell scripts are **NOT** allowed.
- the installer should add
```bash
# shpkg-name! package-name
# shpkg-desc! package-description
# shpkg-by! package-author
```
at the top of the file, **AFTER** the shebang line.
## how can i add my package here?
1. fork the git repository `https://github.com/shpkg/repo`.
2. add your script to /. for example, if i wanted to add *betterfetch*, i would create a file called `betterfetch.sh`. make sure that you added the shpkg properties after the shebang line.
3. open a pull request. do not forget to answer the questions in the pull request template.
4. wait! congrats, you just submitted your first ever sh package!

## what's with the name? you always say shpkg/shpm instead shpkg.
shpm was the codename of the project. but it sounds cool, so we use both.
