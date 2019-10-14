# Unity + Git + Git LFS

This is a template for setting up Unity + Git + Git LFS. 

There are a couple of challenges when it comes to using git (or version control software in general) with Unity:

- Binary assets - commit history, merge conflicts, etc. are near impossible for a human to read. We can solve this by serializing assets, e.g. turning Unity scenes into a text format.
- Large files (large 3D models, big spritesheets, etc.) - GitHub warns you at 50mb and caps you at 100mb. We can solve this with [Git LFS](https://git-lfs.github.com/)

## Setup

To set up a new repository for a Unity project with Git and Git LFS:

- Configure Unity:
  - Open the editor settings window (`Edit > Project Settings > Editor`).
  - Set Asset Serialization mode to "Force Text." It should default to this in the latest version of unity.
  - Set Version Control mode to "Visiable Meta Files."
  - Save your project.
- Adding .gitignore and .gitattributes:
  - Open up your Unity project folder in file explorer/finder. It's the folder that contains "Assets/", "ProjectSettings/", "Packages/", etc. In other words, select the folder one directory up from "Assets/". One quick way to get there from Unity: right click on "Assets" in your Project window and select "Show in Explorer".
  - Add the .gitignore and .gitattributes files contained in this repository to your project folder. You can download a zip [here](https://github.com/mikewesthad/unity-git-and-lfs/archive/master.zip). Again, they should be next to - not inside - your "Assets" folder.
- Set up a new repository. There are a number of ways to do this. The way described below is through [GitHub Desktop](https://desktop.github.com/).
  - Create a new repository in your Unity project:
    - `File > Add local repository`
    - Under local path, select the folder that contains your Unity project, i.e. select 
    - It will warn you that this isn't a git repo and give you a link to "create a repository" here. Click that.
    - On the next screen, click "create repository".  
- Set up Git LFS:
  - If you haven't already, install [Git LFS](https://git-lfs.github.com).
  - Navigate to your repository and run `git lfs install` in your command prompt/terminal. If you have your repository selected in  GitHub Desktop, you can click `Repository > Open in Command Prompt` from the toolbar to open up a terminal window. Type in `git lfs install` and hit enter. You should see a message like "Git LFS initialized"
- Publish your repository:
  - Head to GitHub Desktop and select your repository.
  - Click the "Publish repository" button near the top of the screen.
  - If you are creating this repository for a project in class, uncheck "Keep this code private".
  - Click "Publish repository".

## Resources

- [How to Git with Unity post](https://thoughtbot.com/blog/how-to-git-with-unity)
- [Unity's manual of VCS](https://docs.unity3d.com/Manual/VersionControl.html)
