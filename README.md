Dotfiles without symlinks
=========================
This is a bootstrap script that gets you started with maintaining your dotfiles in a Git repository. The setup follows a concept described by [Eli Barzilay](http://www.xxeo.com/archives/2010/02/16/dotfiles-in-git-finally-did-it.html#comment-126903) and [Masukomi](http://weblog.masukomi.org/2011/12/19/serving-octopress-from-a-self-hosted-git-repository/). I found the final hint about core.worktree in [deanoj's blog](http://www.deanoj.co.uk/programming/git/using-git-and-a-post-receive-hook-script-for-auto-deployment/).

Workflow
========
Development of dotfiles with this setup is no different from any other git workflow.

The one important thing to remember is that changes to any of the dot files in the actual `$TARGET_DIR` directory will not make it into the repository. Instead, dotfiles must be changed in the `$WORK_DIR`, tested and then committed to the repository. The post-receive hook will take care of checking the changes out into the `$TARGET_DIR`.
