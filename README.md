# git-bump-version
A git tool to [keep a changelog](https://keepachangelog.com/en/1.0.0/)

# Installation

```
git clone https://github.com/gabriel-araujjo/git-bump-version.git
cd git-bump-version
sudo cp git-bump-version /usr/local/bin
sudo mkdir -P /usr/local/share/man/man1
sudo cp git-bump-version.1 /usr/local/share/man/man1
```

# Usage

```
USAGE:
        git bump-version [--help | -h] [--major | -M] [--minor | -n]
                [--patch | -p] [<version>]

DESCRIPTION:
        This command shifts up the 'Unreleased' section on GHANGELOG.md
        so that a new section, named with the version passed by argument,
        is created to keep the modifications that was unreleased.

        It also changes version of the root cmake project if a CMakeLists.txt
        is found.

        On success it also creates a tag to the version.

        If some error occur during the version bumping the chages are
        immediately reverted.

        GHANGELOG.md will be automaticaly created if it doesn't exist.

OPTIONS:
        -h, --help      Prints help information.
        -M, --major     Tweaks version major number.
                        Ignored if version argument is present.
        -m, --minor     Tweaks version minor number.
                        Ignored if version argument is present.
        -p, --patch     Tweaks version patch number.
                        Ignored if version argument is present.
        -P, --push      Also push the modifications to origin.

        If --major, --minor and --patch are present twice or more, only the
        last one is applied.

EXAMPLES:
        git bump-version 1.0.0
        git bump-version --major
        git bump-version --minor

ARGUMENTS:
        <version>

        The version argument must follow the semantic versioning 2.0.0* spec
        so that it obey to the following format

                MAJOR.MINOR.PATCH

        where MAJOR, MINOR and PATCH are decimal integer greater than or
        equal to zero. No leading zero is allowed in any part.

        [*] Currently this command does not support versions with prerelease
            or buildmetadatas strings.
            
```
