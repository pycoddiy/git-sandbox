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
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        LICENSE
        README.md
        app.js
```


Add the file that we just created into the git's staging area `$git add app.js`.

3. 