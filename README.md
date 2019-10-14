# Unity + Git + Git LFS

This is a template for setting up Unity + Git + Git Large File Storage (LFS). 

There are a couple of challenges when it comes to using git (or version control software in general) with Unity:

- Binary assets - commit history, merge conflicts, etc. are near impossible for a human to read. We can solve this by serializing assets, e.g. turning Unity scenes into a text format.
- Large files (large 3D models, big spritesheets, etc.) - GitHub warns you at 50mb and caps you at 100mb. We can solve this with [Git LFS](https://git-lfs.github.com/).

## Initial Setup

The initial setup for a project requires a few steps, but you only have to do it once per project. This guide assumes you have an existing Unity project that you want to set up as a git repository. If you don't, just create a blank new one. To set up a Unity project with Git and Git LFS:

- Configure Unity's project settings:
  - Open the editor settings window (`Edit > Project Settings > Editor`).
  - Set Asset Serialization mode to "Force Text." It should default to this in the latest version of unity.
  - Set Version Control mode to "Visiable Meta Files."
  - Save your project.
- Adding .gitignore and .gitattributes:
  - Open up your Unity project folder in file explorer/finder. It's the folder that contains "Assets/", "ProjectSettings/", "Packages/", etc. In other words, select the folder one directory up from "Assets/". One quick way to get there from Unity, right click on "Assets" in your Project window and select "Show in Explorer".
  - Add the .gitignore and .gitattributes files contained in this repository to your project folder. You can download a zip [here](https://github.com/mikewesthad/unity-git-and-lfs/archive/master.zip). Again, they should be next to - not inside - your "Assets" folder.
  - It's important that you do this step first before creating the repository so that the appropriate files are ignored by git and the large files are set up to go to large file storage (LFS).
- Set up a new repository. There are a number of ways to do this. The way described below is through [GitHub Desktop](https://desktop.github.com/).
  - Create a new repository in your Unity project:
    - `File > Add local repository`
    - Under local path, select the folder that contains your Unity project (i.e. one up from "Assets").
    - It will warn you that this isn't a git repo and give you a link to "create a repository" here. Click that.
    - On the next screen, click "create repository".
- Set up Git LFS:
  - If you haven't already, install [Git LFS](https://git-lfs.github.com).
  - Navigate to your repository and run `git lfs install` in your command prompt/terminal. If you have your repository selected in  GitHub Desktop, you can click `Repository > Open in Command Prompt` from the toolbar to open up a terminal window. Type in `git lfs install` and hit enter. You should see a message like "Git LFS initialized".
- Publish your repository:
  - Head to GitHub Desktop and select your repository.
  - Click the "Publish repository" button near the top of the screen.
  - If you are creating this repository for a project in class, uncheck "Keep this code private".
  - Click "Publish repository".

## Maintenance

Now that the repository is all set up, you can simply commit and push/pull as you work on the project! If you want to set up the repository on a new machine, simply use GitHub Desktop `File > Clone Repository` and select the repository.

One thing to note, the free plan of Git LFS comes with 1g of storage total and 1g of bandwidth per billing cycle/month. Anything you push/pull from LFS counts against that. You can see your current usage under `Settings > Billing`.

## Resources

- [How to Git with Unity post](https://thoughtbot.com/blog/how-to-git-with-unity)
- [Unity's manual of VCS](https://docs.unity3d.com/Manual/VersionControl.html)
