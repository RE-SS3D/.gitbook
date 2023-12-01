# Using GitHub

{% embed url="https://github.com/RE-SS3D" %}
Our GitHub organization.
{% endembed %}

### Git Clients

To get a hold of the project, you need a git client. Git is the software that manages the source. GitHub is the website that we use to host it. If you are new, [GitHub Desktop](https://desktop.github.com/) is easiest for beginners.

### Our Repositories

{% tabs %}
{% tab title="SS3D" %}
{% embed url="https://github.com/RE-SS3D/SS3D" %}
Our **game** repo.
{% endembed %}

The game repository is the ~~only~~ primary repository the most of the contributors will be working on. The game is made by a collection of both artists and coder, the two groups couldn't do it without each other.
{% endtab %}

{% tab title="Art" %}
{% embed url="https://github.com/RE-SS3D/SS3D-Art" %}
Our **art** repo.
{% endembed %}

The art repo is the one repo where artists ~~can get away from the coders for a bit~~ contribute source files as to make it easier for editing an art asset later. (This repo may get nested into the game repo, reducing work to export assets to the game from here.)
{% endtab %}

{% tab title="CentCom" %}
{% embed url="https://github.com/RE-SS3D/SS3D-CentCom" %}
Our **server** repo.
{% endembed %}

The server repo is where ~~know one dares to look~~ we host the central server which, as you might have guessed, handles the multiplayer networking.
{% endtab %}

{% tab title="Website" %}
{% embed url="https://github.com/RE-SS3D/SS3D-Website" %}
Our **website** repo.
{% endembed %}

Ah the infamous website repo, ~~if you can't guess this one then we're no longer friends~~ is where we develop and host our website from.&#x20;
{% endtab %}
{% endtabs %}

### Forking the Repository

To start contributing via GitHub, first you should fork this GitHub repository, using the 'Fork' button in the upper right corner of this page. Naturally, this requires a GitHub account. You will commit your changes to your fork and then make a pull request to merge it into our repository. Learn more about pull requests [here](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-comparing-branches-in-pull-requests).

Over time your fork will become outdated as the main project's repository continues to be added upon. GitHub has made a [pretty clear guide](https://help.github.com/articles/syncing-a-fork/) on how to sync your fork, to keep it up to date with the SS3D repository.

### Reporting Bugs

Before reporting a bug, please check the [our issues](https://github.com/RE-SS3D/SS3D/issues) to see if the bug has already reported.

If you are unfamiliar with issues, GitHub has a helpful guide [here](https://guides.github.com/features/issues/). Use one of the templates when creating your issue, as the information it requests helps you help us help you more efficiently.

Explain the problem clearly and include any additional details to help maintainers reproduce the problem:

* **Use a clear and descriptive title** for the issue to identify the problem.
* **Describe the steps to reproduce the problem** as specifically and detailed as possible.
* **Describe the behavior you observed** and point out the problem with that behavior.
* **Describe the expected behavior** that should happen instead.
* **Include pictures/videos** to show the steps taken to demonstrate the problem.
* **Include your game version and OS** to help track if the problem is version specific.
* **Include your game settings** to help track if the problem is settings specific.
* **If you're reporting a game crash**, include a crash report with the error log. It's location depends on your operating system, so follow [this official guide](https://docs.unity3d.com/Manual/LogFiles.html).
* **If the problem isn't triggered by a specific action**, describe what you were doing before the problem happened.

### Pull Requests

Pull requests allow the maintainers to review any changes and verify they are wanted and don't break anything in the existing project. Similarly to issues, you should use the template when making a new PR and provide as much detail as possible.

* Pull requests should merge into the _develop_ branch.
* The title and description should be clear and concise.
* If the PR is attempting to fix an issue, reference the issue number in the PR description ("Fixes #number").
* Include pictures/videos in your pull request whenever possible.

### Assigning Issues

Our GitHub issues can be self-assigned using basic commands (see below). This is helpful for contributors to claim an issue without the assistance of a maintainer.

Type the following command as a comment on the issue in question.\
`Assign me` - assigns you to the issue.\
`Unassign me` - unassigns you from the issue.

### Commit Messages

* Use the present imperative tense ("Add feature" not "Added feature", "Move cursor to..." not "Moves cursor to...").
* Limit the first line to 72 characters or less.
* Reference issues and pull requests liberally after the first line.
