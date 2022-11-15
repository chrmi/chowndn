# chowndn 

(**Ch**ange **Own**er from **D**ead **N**ame)

A command line tool for people of transgender experience to replace their dead name within a Git repo.  See [chowndn.com](https://chowndn.com).

![Transgender Flag](docs/Transgender_Pride_flag.svg)
*Transgender Pride flag from [Wikipedia](https://en.wikipedia.org/wiki/Transgender_flag)

This repo is currently _VAPORWARE_ -- it does not have any functionality beyond providing a CLI interface to start developing on.

The __primary__ purpose of releasing a functionally non-working repository is to provide a framework to problem solve a difficult problem -- how to rewrite history within a Git repo without compromising an existing codebase.

The __secondary__ purpose of releasing a bare-bones scaffold is to encourage community involvement from a diverse and inclusive audience, who would benefit from learning Rust and Git along the way.  By starting from scratch, we have the opportunity to learn these tools from humble beginnings without the pressure of coming in with a particular skill set.  Imposter syndrome is real -- please do not let it prevent you from leveraging this project as a means to learn and connect with the community!

Ideally, this tool will be able to checkout and commit in-place rewrites to keep the original repo intact.  If this is not possible, or as an alternate implementation offered through an option flag, a new repo instance could be generated with the desired name changes.  The latter will not work for many use cases, but could still be sufficient for some.


Basic command interface (see Makefile):

```
chowndn version
chowndn scan Jack ./myrepo
chowndn replace Jack Jill ./myrepo
```

Expected workflow:
* Clone a repo.
* Create a working branch from main.
* Scan for original name instances.  Save this output to a file.
* Replace instances of deadname with the new name.  Save this output to a file.
* Diff the two files to ensure only the modifications desired are present.

Unknown handling:
* Rename the main branch, and rename the working branch to main.
* Force push the new main branch.  For each non-temporary branch, set its origin to the new main.

Careful thought and Git expertise will be critical to solving this problem correctly.  See the GitHub Issues for this repo as a means of having discussions on approaching individual technical challenges.  For informal discussion, use the #chowndn hashtag and tag [@chrmi](https://tech.lgbt/@chrmi) on Mastodon.
