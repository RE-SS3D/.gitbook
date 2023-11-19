---
description: Defining what a release version means.
---

# Releases

## Release **Versioning**

The release naming is defined by <mark style="color:purple;">**`gamestate`**</mark>**`.`**<mark style="color:red;">**`major`**</mark>`.`<mark style="color:orange;">**`minor`**</mark>`.`<mark style="color:yellow;">**`hotfix`**</mark>\
In which the rules are:

<details>

<summary><mark style="color:purple;">Game State</mark></summary>

Refers to the overall state of the game. `0.x.x.x` version indicates the game is still in a alpha/beta/pre-complete phase. Once we have reached a point where we have ported over most of the systems and content from ss13, and feel satisfied, we can then move to `1.x.x.x` and b~~e~~yond with new content.

</details>

<details>

<summary><mark style="color:red;">Major</mark></summary>

Refers to large **milestone**. Major milestones are large changes that may span numerous months and PRs.

An example of a major milestone would be several new systems or reworked systems that together make up a large change in how the game feels. Milestones will have their version number in their name. e.g. "**0.2 - Milestone Name"**.

</details>

<details>

<summary><mark style="color:orange;">Minor</mark></summary>

Refers to small **milestones**. Minor milestones are usually a single large system or a collection of smaller changes.

An example might be a rework to the health system, or a collection of new content for a couple recently added systems.&#x20;

</details>

<details>

<summary><mark style="color:yellow;">Hotfix</mark></summary>

Refers to quick fixes post a <mark style="color:red;">major</mark> or <mark style="color:orange;">minor</mark> release. An example would be a critical bug that was undetected until after release and needs to be quickly fixed.

Any example might be a bug that prevents players from joining and needs to be updated in a release ASAP instead of waiting for the next <mark style="color:orange;">minor</mark> release.

</details>

## Automated Releases

Soon we will move to automated releases much like many of the SS13 servers and such. First they will likely start off as monthly releases but after we gain a lot of momentum we will eventually move to nightly releases.

These will be registered as <mark style="color:yellow;">hotfix</mark> releases. Devs will still be able to push manual releases at anytime for <mark style="color:yellow;">hotfixes</mark> as well.
