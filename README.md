git-docs
========

Documentation of Interesting Git Things

---

##Merge One Repository into Another

There may be that odd scenario that you want to move code from one repository into another. I.e. moving a repo from SourceForge into GitHub, you can follow the following process.

_This assume you've already created a project on GitHub_

SourceForge Repository: `http://git.code.sf.net/p/myUser/myProject`

GitHub Repostiory: `https://github.com/myUser/myProject`

```bash
$ git clone https://github.com/myUser/myProject.git
$ git remote add other http://git.code.sf.net/p/myUser/myProject.git
$ git fetch other
$ git checkout -b other-master other/master
$ git checkout master
$ git merge other-master
$ git add -A
$ git commit -am "Merged from old repo"
$ git push -u origin master
```

Now you're done the __origin__ now has the same code base including history as __other__
