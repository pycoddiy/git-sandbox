# Creating the new project from scratch

## Essential project files
1. Open terminal and locate where your projects reside. I prefer all coding projects to reside in the home directory under `repos`, such as `$ cd ~/repos`.

2. Create new project directory `project-name`, e.g. for the `git-sandbox` project run `$ mkdir git-sandbox`.

3. Now create a few essential files every well-designed repository should have.

    3.1 `README.md` using `$ touch README.md` command.

    3.2 `LICENSE` using `$ touch LICENSE` command.

4. Check if you have git installed by runnint `$ git --version` command. If an error is displayed, refer to the git installation instructions for your OS (not included in this documentation). Initialize git for the project with `$ git init`.

5. Now you can open VSCode for file editing `$ code .`

## Editing README.md in VSCode
It is recommended to open the preview of the file to see the rendering results for the markup language (VSCode shortcut Ctrl+K then V).

There is not defined structure for the document. The key to remember is that this is the first file most people will read about your project and will judge your project quality based on this first impression.

A good README.md file typically covers the following aspects:

* **Project Description:** A brief summary of what your project does.

* **Installation Instructions:** How to set up and run the project. 

* **Usage Examples:** Code snippets demonstrating how to use key features.

* **Contribution Guidelines:** How others can contribute to the project. 

* **License Information:** Clearly state the license under which the project is released. It is okay to reference to the respective LICENSE file that we just created.

README file typically uses the Markup Language (MD). Please refere to the respective [documentation](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) how to write MD files.

## Editing LICENSE in VSCode

The license file should include the following information:

* **License Title:** The name of the license being used (e.g., "MIT License", "Apache License 2.0").

* **Copyright Notice:** The copyright holder's name and year. 

* **Permissions Granted:** What the user is allowed to do with the software (e.g., use, modify, distribute).

* **Restrictions:** Any limitations on usage, such as commercial use restrictions or attribution requirements.

* **Liability Disclaimer:** Statements regarding the software being provided "as is" without warranties.

* **Contact Information:** How to reach the copyright holder for further inquiries. 

Refer to the further reading or seek for a legal advice as needed regarding the best options for your project.

## Continuing with git

You will not see anything as a result of `$git init` we ran while creating the project. This is because the initialization results are stored in the hidden directory `.git`. To see this directory run `ls -a` in your project's root directory. Likewise you will not see `.git` from withing VSCode.

Now, let's continue in VSCode.

1. Create the new file `app.js` and add some useful code into it, e.g.

```js
console.log("Hello World!")
```

2. Open Terminal within VSCode (you can always switch to your already opened terminal window, if you want, but it is not highly productive. My advice is to open Terminal right within VSCode to minimize windows switching. Run `$ git status` in the Terminal to see the files with changes:

```bash
git status
```
```console
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        LICENSE
        README.md
        app.js
```


3. Run Add the file that we just created into the git's staging area `$ git add LICENSE README.md app.js` to add all modified files to the staging area. It is not a bad practice to add files one by one by specifying their names to control what you add and to avoid a mess in the staging area --- know exaclt what you're adding.

4. Run `$ git status` to make sure the files are in the staging area:

```console
 committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   LICENSE
        new file:   README.md
        new file:   app.js
```

5. Now we are ready to make an initial commit of the project. To do that you need to run `$ git commit -m "Description of the changes being committed"`. The option `-m` followed by the string describes what exactly changes are being committed. Do not underestimate the necessity to provide meaningful comments. If later you will need to find something in the change history, you will really thank those who did not ignore to provide a meaningful message for the commit.

```
git commit -m "Initial commit of the project repo, that includes the JS app, README.md with insturctions, how to start the project from scratch, and the LICENSE file"

 3 files changed, 87 insertions(+)
 create mode 100644 LICENSE
 create mode 100644 README.md
 create mode 100644 app.js
```

6. Add `.gitignore`. From terminal run `$ touch .gitignore`. Then edit the file in VSCode by adding files and file extensions you do not want to be ever committed. Typically these are derivative files of your local runs, e.g. log files (`*.log`, `*.tmp`), or if you program in Nuxt or TypeScript, your local project repository will contain resulting HTML and JS files --- these are derivative files. You do not necessarily want to commiit them. You can always regenerate them on a target system. Use your judgement to decide what is essential and what is secondary/derivative. For security reasons never commit secrets, passwords, private and sensitive data.

7. Repeat steps by adding new (.gitignore) and modified files (README.md, etc) into the staging area. Then commit them with additional `-m` message. Do not forget to check the status frequently with `$ git status`.

8. Now it's a good time to get local repository pushed to the remote. We will use GitHub as a remote repo. Log in to GitHub and add New repository there. We will use the same name `git-sandbox` as for the local project.

9. Do not add README.md and LICENSE (we will push these from the local repo). Just add a meaningful repo description. In the end the GitHub will offer instructions how to push local repo to GitHub:

```
git remote add origin https://github.com/pycoddiy/git-sandbox.git
git branch -M main
git push -u origin main
```

10. After running above commands check out the GitHub repo. It is now synchronized with your local repo. You are good to continue working with the README to add extra instructions. But before doing this, let us follow the best practices by working with branches. It is not the best practice push directly to `main` branch, which is supposed to be the up-to-date branch of the project, from which other people fetch stable working sources. If you perform the push into that branch and you code breaks someing, then other people won't be able to use the project.

11. To mitigate this risk, a developer creates a custom branche with proposed changes, pushes it to the remote so that others can inspect changes. If the changes look good, the custom branch is merged into the `main`. To create the branch, use `$ git branch <branch-name>`. Since our changes will aim at README improvements, it would be wise to create something like this `$ git branch improve-readme`.

12. Run `$ git branch` to see that you're still on the `main` branch. To switch to another branch you run `$ git checkout improve-readme`. Ensure you are on the new branch by running `$ git branch`.

13. After completing edits to the README.md document,  run `$ git add README.md`. Check the status `$ git status` and then perform the commit. Push the branch to the remote `$ git push -u origin improve-readme`. Get back to GitHub.

