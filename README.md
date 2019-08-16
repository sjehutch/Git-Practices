## Contributing

### Preamble 
We encourage all developers to make mistakes in the beginning. This document is meant to create harmonious and continuous development across all teams. When something does not make sense please do not ever hesitate to ask or get clarification. We are first and foremost a team. Please feel free to make reccomendations on changes to the process . 

The Direct Team will have a strict set of guidelines for how we check in code. This ensures that we have high quality code delivered on a continuous basis.
#### Submitting a Pull Request (PR)

All code submitted for Direct must go through a pull request and no direct changes are allowed on developer or master. This is a peer reviewed cycle which allows us to maintain a high level of quality in our code.
Before you submit your Pull Request (PR) you must abide by the following guidelines:
* Work must be done on a local branch associated with the user name and work item number done either through Visual Studio or via the command prompt:
```
git checkout -b my-fix-branch master
```
* Ensure all unit tests pass through running the suite with Visual Studio or the command prompt.
* Create your commit, following code style guidelines, and including appropriate test cases. In the case of any new code or fixes, it must be accompanied by unit tests.
* Commit your changes using a descriptive commit message that follows our commit message conventions. Adherence to these conventions is necessary because release notes are automatically generated from these messages. Either use Visual Studio or via the command prompt to check in your code:
```
git commit -a
```
Note: the optional commit -a command line option will automatically “add” and “rm” edited files.
* Push your branch to Dev Ops either through Visual Studio or via the command prompt:
```
git push origin my-fix-branch
```
* In Visual Studio, create a Pull Request, in which you will then receive feedback from a team member
* If changes are suggested then:
    * Make the required updates
    * Re-run the test suites to ensure tests are still passing.
    * Rebase your branch and re-push to VSTS either via Visual Studio or the command prompt:
```
git rebase master -i
git push -f
```
* When your PR is merged, we will use the Squash Commits to ensure a single commit for the feature.
##### After Your Pull Request is Merged

After your pull request is merged, you can safely delete your branch and pull the changes from the main (upstream) repository:
* Delete the remote branch on VSTS either through the Visual Studio or your local shell as follows:
```
git push origin --delete my-fix-branch
```
* Check out the master branch through Visual Studio or the command prompt:
```
git checkout master -f
```
* Delete the local branch through Visual Studio or the command prompt:
```
git branch -D my-fix-branch
```
* Update your master with the latest upstream version through Visual Studio or the command prompt:
```
git pull --ff upstream master
```
#### Commit Message Guidelines

We have very precise rules over how our git commit messages can be formatted. This leads to more readable messages that are easy to follow when looking through the project history. But also, we use the git commit messages to generate the Direct change log.
##### Commit Message Format

Each commit message consists of a **header**, a **body** and a **footer**. The header has a special format that includes a type, a scope and a subject:
```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```
The  **header** is mandatory and the  **scope** of the **header** is optional.
Any line of the commit message cannot be longer 100 characters! This allows the message to be easier to read on Visual Studio Online as well as in various git tools.
 ##### Reverting a Commit
If the commit reverts a previous commit, it should begin with revert:, followed by the header of the reverted commit. In the body it should say: This reverts commit <hash>., where the hash is the SHA of the commit being reverted.
 
 #### Type

Must be one of the following:
* **feat**: A new feature
* **fix**: A bug fix
* **docs**: Documentation only changes
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
* **refactor**: A code change that neither fixes a bug nor adds a feature
* **perf**: A code change that improves performance
* **test**: Adding missing tests
* **chore**: Changes to the build process or auxiliary tools and libraries such as documentation generation
##### Scope
The scope could be anything specifying place of the commit change. For example Shell, Logging, Infrastructure, etc.
##### Subject
The subject contains succinct description of the change:
* use the imperative, present tense: “change” not “changed” nor “changes”
* don’t capitalize first letter
* no dot (.) at the end
##### Body
Just as in the subject, use the imperative, present tense: “change” not “changed” nor “changes”. The body should include the motivation for the change and contrast this with previous behavior.
##### Footer
The footer should contain any information about **Breaking Changes** and is also the place to reference GitHub issues that this commit Closes.
Breaking Changes should start with the word ```BREAKING CHANGE:``` with a space or two newlines. The rest of the commit message is then used for this.
