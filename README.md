# tekken7
#trying/testing to upload tekken 7 games on github



Methodology:

Uploading massive files to GitHub can be a bit of a headache because standard Git commands have a 100 MB file limit, and the web uploader isn't much better for "giant" archives.

To get this done effectively, you generally have three paths depending on just how big this file is.

1. The Best Way: Git Large File Storage (LFS)
If your ZIP file is over 100 MB, you should use Git LFS. It replaces large files with text pointers inside Git, while storing the actual file on a remote server.

How to set it up:
Download and install the Git LFS extension.

Open your terminal/command prompt in your local repository folder.

Initialize LFS: git lfs install

Track your ZIP files: git lfs track "*.zip" (This creates a .gitattributes file. Make sure to commit this file!)

Add and commit as usual: git add yourfile.zip git commit -m "Add giant zip file via LFS" git push origin main

Note on Quotas: GitHub's free tier for LFS typically includes 1 GB of storage and 1 GB of bandwidth per month. If your file is larger than that, you might need to purchase more data or use the next method.

2. The "I just want people to download it" Way: GitHub Releases
If you don't need the ZIP file to live inside your source code tree and just want it available for others to download, use Releases. This is often the best "hack" for large files.

Go to your repository on GitHub.

Click Releases (on the right-hand sidebar).

Click Draft a new release.

Upload your ZIP file into the "Attach binaries" box.

Limit: Files can be up to 2 GB each.

3. The "Manual" Way: Splitting the Archive
If you can't use LFS and the file is too big for a single upload, you can split the ZIP into smaller chunks (e.g., 50 MB each).

On Mac/Linux: split -b 50m giant_file.zip "giant_file.zip.part"

On Windows: Use a tool like 7-Zip to "Split to volumes."

You then upload all the parts. To use them, the person downloading would have to "re-join" them. (It's a bit clunky, but it works in a pinch!)

## Turns out tekken 7 is 40GB zip and isnt possible here all together and doing seprately would be a pain in the ass for downloader so imma try huggingface and link it here
[huggingface  tekken7](https://huggingface.co/datasets/hmd911/tekken7)
