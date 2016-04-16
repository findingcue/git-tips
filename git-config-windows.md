# To set default 'commit' editor

Sets Notepad++ editor as default GIT commit editor.Make sure Notepad++ is installed.

    $ git config --global core.editor "'c:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"

# To set your email address
Setting your email address for every repository on your computer:

	$ git config --global user.email "john@hotmail.com"

Setting your email address for a single repository: You may need to set a different email address for a single repository, such as a work email address for a work-related project.

	$ git config user.email "john@work.com"
    
# To configure difftool & diffmerge
[SourceGear DiffMerge](https://sourcegear.com/diffmerge)

Pre-requisite: 
1. Install SourceGear DiffMerge (64-Bit) available for download from download.cnet.com
2. Make sure environment-variable PATH is appended with path to sgdm.exe

To configure diff tool

    $ git config --global diff.tool diffmerge

NOTE: if after setting below configuration, it still doesn't work then check the 
global-git-config file and makesure difftool cmd is configured with this string: sgdm.exe \"$LOCAL\" \"$REMOTE\"

    $ git config --global difftool.diffmerge.cmd "sgdm.exe \$LOCAL \$REMOTE"

To launch difftool (that are not staged for commit yet)

    $ git difftool

To launch difftool for files that already staged for committed

    git difftool --cached

To configure merge tool

    $ git config --global merge.tool diffmerge
    $ git config --global mergetool.diffmerge.cmd "sgdm.exe --merge --result=\$MERGED \$LOCAL \$BASE \$REMOTE"
    $ git config --global mergetool.diffmerge.trustExitCode true

To launch mergetool

    $ git mergetool

# To ignore certain files
    
    $ git config --global core.excludesfile {filepath e.g. => Test/common/gitconfigfiles/.gitignore}

Following are some examples that have been tested on Windows successfully:

    $ git config --global core.excludesfile common\gitconfigfiles\.gitignore
    $ git config --global core.excludesfile "d:/Development/Projects/repositories/Test/common/gitconfigfiles/.gitignore"
    
