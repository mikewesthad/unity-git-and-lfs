# Unity + Git + Git LFS

This is a tutorial & template for setting up Unity + Git + Git Large File Storage (LFS). 

There are a couple of challenges when it comes to using git (or version control software in general) with Unity:

- Binary assets - commit history, merge conflicts, etc. are near impossible for a human to read. We can solve this by serializing assets, e.g. turning Unity scenes into a text format.
- Large files (large 3D models, big spritesheets, etc.) - GitHub warns you at 50mb and caps you at 100mb. We can solve this with [Git LFS](https://git-lfs.github.com/).

## Initial Setup

The initial setup for a project requires a few steps, but you only have to do it once per project. To set up a Unity project with Git and Git LFS:

### Preparing your Computer

- Create a [GitHub account](https://github.com/join).
- Install the required software on your machine:
  - [Unity](https://unity.com/).
  - [GitHub Desktop](https://desktop.github.com/).
  - [Git LFS](https://git-lfs.github.com).
  - If you are in the IAM labs/classrooms, these should be installed. You may need to open the software center to activate GitHub Desktop.
- Open up GitHub Desktop and login in with your GitHub account.

### Creating the Repository

You can watch a video of this process [here](https://colum2.instructuremedia.com/embed/de36691b-707a-4877-910c-e25b0f0d45aa), or follow along below:

- Create a new repository for your project from GitHub Desktop:
  - `File > New Repository` or `CTRL + N`.
  - Give it a name and choose the local path where it will be created. (If you are in an IAM lab/classroom, do NOT put it on the network home drive AKA z drive.)
- Add the .gitignore and .gitattributes:
  - [Download the files](https://github.com/mikewesthad/unity-git-and-lfs/archive/master.zip) from this repo.
  - Unzip the files and copy over the .gitignore and .gitattributes files to your git repository.
  - Create a commit from GitHub Desktop with those two files.
  - It's important that you do this step first before adding any Unity project files.
- Set up Git LFS:
  - Navigate to your repository and run `git lfs install` in your command prompt/terminal. If you have your repository selected in GitHub Desktop, you can click `Repository > Open in Command Prompt` from the toolbar to open up a terminal window. Type in `git lfs install` and hit enter. You should see a message like "Git LFS initialized".
- Add your Unity project to the repository:
  - Create a new Unity project or grab an existing project.
  - Open up your Unity project folder in file explorer/finder. It's the folder that contains "Assets/", "ProjectSettings/", "Packages/", etc. In other words, select the folder one directory up from "Assets/". One quick way to get there from Unity, right click on "Assets" in your Project window and select "Show in Explorer".
  - Copy all the contents of your project folder into your repository (e.g. "Assets/", "ProjectSettings/", etc.).
- Make a commit of the project:
  - Head back to GitHub desktop.
  - Select your files and make a commit.
- Publish your repository:
  - Head to GitHub Desktop and select your repository.
  - Click the "Publish repository" button near the top of the screen.
  - If you are creating this repository for a project in class, uncheck "Keep this code private".
  - Click "Publish repository".
  - Whew! It's live now. You go straight to where it is stored on GitHub via `Repository > View on GitHub` in the GitHub Desktop toolbar.

Now that the repository is all set up, you can simply commit and push/pull as you work on the project! Make sure to always commit and sync before leaving the lab.

## Cloning the Repository Elsewhere

Now that you've got this Unity project on GitHub, you can "clone" it to a new computer:

- Make sure you have GitHub Desktop + Git LFS + Unity on the computer.
- Open GitHub Desktop and log in.
- Click on `File => Clone Repository..." (or CTRL + SHIFT + O). Choose the repository and the local path where it should be cloned on the computer.
- GitHub Desktop may prompt you to install Git LFS. If it does, allow it. If it doesn't, repeat the process from the previous section where we ran `git lfs install` from a terminal window.

## Notes

One thing to note, the free plan of Git LFS comes with 1g of storage total and 1g of bandwidth per billing cycle/month. Anything you push/pull from LFS counts against that. You can see your current usage under `Settings > Billing`.

## Resources

- [Version control: Effective use, issues and thoughts, from a gamedev perspective](https://www.what-could-possibly-go-wrong.com/version-control/) - a good overview of the uses and challenges of version control in game dev
- [How to Git with Unity](https://thoughtbot.com/blog/how-to-git-with-unity) - a concise post of Git + Unity
- [Unity's manual of VCS](https://docs.unity3d.com/Manual/VersionControl.html)
