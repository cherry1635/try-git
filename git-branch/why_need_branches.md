# Why need branches?

There are 3 branches. only one main branch, and the main branch is for the release version, and other branch for other functions.

As like, rust has a nightly version, it was a more radical branch. because some changes should be through the serious consideration and totally test, and to be the release version.

so most repo will be take the main branch as a release branch and this branch will slower than others, like it will not update so often.

but for me, main branch is a solid version, that just say, something gonna no problem, the user can download, and there is no user complaints.


<h4> download the repo from remote</h4>
git pull == git fetch + git merge.
If you download the remote one, there will be differences for both remote and local.
And there may be the conflicts in `merge`.


