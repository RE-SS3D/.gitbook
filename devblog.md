---
description: Devblog creation process.
cover: .gitbook/assets/Bug_CargoAnimals.png
coverY: 0
---

# 📰 Devblog

_Devblogs are usually made by **CosmicCoincidence** but this page is written so that any team member (or contributor really) can make it._

**Currently devblogs are being made quarterly, but as progress picks up again we may switch back to monthly.**

Simply put, the idea is to showcase all (note-worthy) contributions during a given period, but it's a bit of a process (you will need to know [GitHub](http://127.0.0.1:5000/s/oTyzvarT8sBLwLdFnIjo/introduction/using-github) for this):

<details>

<summary>Step -1: Foresight</summary>

If you know in advance that you will be responsible for creating the devblog, then I **highly** recommend you to follow the github repos & contribution channels in the discord throughout the month/quarter, so that you are more familiar with them when the time comes to write about them. Also ask contributors to provide photos/videos of their work in advance so you don't need to do it yourself.

</details>

<details>

<summary>Step 0: New Release</summary>

Make sure a new release has been made recently. If automated releases haven't been configured yet, and you are the one responsible for the making the the devblog, then you are also likely responsible for make the release manually. See the release page for info.

</details>

<details>

<summary>Step 1: Blog - Set Up</summary>

1. Fork the [website repository](https://github.com/RE-SS3D/SS3D-Website) if you haven't already.\

2. Open & read the "devblog-format.md" file in the "\_drafts" folder. This file details how to format the blog file itself. You can use it or another devblog file (in the "\_posts" folder as a template for your blog file.\

3. Name your file like so: `year(full)-month-30-year(short).month` and place it in the "\_posts" folder. (The month in question is the month you are writing the blog, it is for the month you are writing about. If the blog is a quarterly blog, use the last month of the quarter here.)\

4. Follow your template file and fill in the 'title' and other variables.\
   The 'title' should look like `year(short).month` if a monthly blog; or `year(short).month-month` if a quarterly blog, first 'month' representing start of the quarter, second 'month' representing the end.\
   The 'release' should match the tag of the latest GitHub release made in [Step: 0](devblog.md#step-0-new-release).\
   Also, don't change the time...

</details>

<details>

<summary>Step 2: Blog - Contributions</summary>

\*Make sure all contributions are credited!\*

### **Art Contributions:**

Must be submitted via the art channels on discord or merged to the game (SS3D) or art (SS3D-Art) repos (if submitted via discord, add the submissions to the [googledrive](https://drive.google.com/drive/folders/1n9oCtlF6snAzWmzeD8wjdCuiOo-a1\_R4?usp=share\_link) and credit the file with the contributor's name in the credits file).

Art contributions usually don't need much explanation so a sentence for each usually will suffice. These should always have some media (image or video) to display.

### **Technical Contributions:**

Must be submitted via merged to one of our github repos.

Technical contributions are usually split into 2 types; large ones are given their own sections with more detailed explanations and maybe even media, small ones are collected into the 'Details' section and listed by contributor name.

### **Media:**

Place the artwork in `/assets/img/art/[contributor]/`.

Place the other media in `/assets/img/posts/[period]/`.

* photos must be 800x600px resolution unless they are artwork (like wallpapers or logos).
* videos must be 800x600px or 1280x720px resolution to be added to the site directly (other resolutions can be uploaded to youtube and linked otherwise).
* media must be named accordingly (e.g. 'Contributor\_Contribution.media')!

### Extras:

* Add artwork to the "art.md" page too.

</details>

<details>

<summary>Step 3: Pull Request</summary>

Make your pull-request to the 'release' branch and wait for a @Centcom or @Website-Maintainer to merge it.

</details>
