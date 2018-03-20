`push_dir_to_repo` is used to upload a directory to a remote Git
repository, *replacing its existing content*.  A common use-case is to
push built documentation up to GitHub pages.

## Usage

In the simplest case, the following command takes the contents of the
`docs` directory and uploads it to the remote repository,
*overwriting* its existing content:

```
push_docs_to_repo.py docs git@github.com:my_org/my_docs_repo
```

In the following more detailed example, we have just built some Sphinx
documentation in the `_build/html` directory.  We now push the HTML
files to our `gh-pages` branch:

```
push_docs_to_repo.py \
  --branch gh-pages \
  --email commitbot@commitbot \
  --committer "My Uploader Name" \
  --message "Update website" \
  --force \
     _build/html git@github.com:myorg/myrepo
```
