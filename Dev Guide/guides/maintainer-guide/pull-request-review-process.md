# Pull request review process

When needed, contributors might need to review PRs

To ease out the process, we'll walk through all the points need to be tackled when reviewing.

### Check the Target branch, check the source branch

1. **Check the target branch.**
   * Most of the PRs should be `develop`, but some might be updating a feature or a preview feature, make sure the feature is not supposed to be a test nor experimental.
2. **Source branch should be up-to-date with the** `develop` **branch.**
   * It is not allowed to merge non up-do-date branches to `develop`, even if there's no merge conflicts.

### Check PR's information

1. **Revise the PR's textual information.**
   * Make sure the title doesn't contain the `[WIP]` tag. If you feel the PR is completed, warn the author.
   * Make sure the PR describes clearly how that PR will change `develop`.
2. **Make sure the known issues are present in the PR description.**&#x20;
   * See link '[Turn known issues into Github issues](pull-request-review-process.md#turn-known-issues-into-github-issues)' for more info.

### Check and make the tests

You can follow the instruction of the [Running ](../running-the-project/)section to learn how to run with the different set ups of this section.

1. **Revise the tests log.**
   * Before continuing, it is proper to check if all the checks were passed on the tests runner.
   * If any tests have failed, warn the author.
2. **Playtest in the editor.**
   * Playtest all the feature in the editor, as it is the most safe way to playtest most of the time.
   * If any issues appear here, warn the author and create a small video or a very detailed comment on the PR.
3. **Make a build.**
   * If the build fails, warn the author and screenshot the build error message, add said screenshot in a comment on the PR.
4. **Play the build as the host.**
   * If any errors appear in this built version, warn the author and create a small video or a very detailed comment on the PR.
   * Note that all playtest in built executables should explore the feature as much as possible, to detect bugs as early as possible.
5. **Play the build as the host and another as a client.**
   * If any errors appear in this built version, warn the author and create a small video or a very detailed comment on the PR.
6. **Play the build as the server and another as a client.**
   * If any errors appear in this built version, warn the author and create a small video or a very detailed comment on the PR.
7. **Play the build as the server and more than one as clients.**
   * If any errors appear in this built version, warn the author and create a small video or a very detailed comment on the PR.

### Check the file organization and naming

1. **Make sure no unwanted files were committed.**
   * &#x20;we don't want changes that are not related to the PR.
   * Warn the author about, question why that file is being submitted.
2. **Make sure the committed files follow our** [**file naming and organization**](../../introduction/file-naming-and-organization/)**.**

### **Check the PR content**

1. Make sure no **unwanted or unrelated** changes are present on the PR.
   * we want PR to be concise as much as possible, changes that do not fit the description of the PR should simply not be there.
2. Make sure big PR are either :&#x20;
   1. Completely new addings. It's fine for PRs to be big if they don't modify preexisting part of the code.
   2. Complete removal. If we ever need to completely remove something, it's fine if it's big.
   3. Changes very focused on one aspect : adding a particular attribute project wise, fixing a given style project wise, those are all acceptable changes.

### Check the code

1. **Make sure all the code follows the** [**C# style guide**](../../guidelines/the-c-style-guide/)**.**&#x20;
   * This is not the best way nor it is infallible, but we still don't have any syntax linting.
2. **Make sure the best architecture to your knowledge is being used.**&#x20;
   * Always ask why things are in that way if you feel something can be done better or don't know how it works.
3. **Don't ask for micro optimization unless it's really obvious.**&#x20;
   * We have close to zero performance tests at this point. We don't want to over optimize at the cost of ruining readability and introducing hard bugs to solve, when the performance need is probably not even there.

### Ask for documentation

1. **Ask for thorough comments when necessary.**&#x20;
   * Insist on it especially when something is public.
2. **Ask for independent documentation when a new feature is added.**
   * The doc should be user oriented, it should mainly answer the question "how do I use this feature?"&#x20;
   * If the contributor wants to add some technical details in it, check that it's focusing on a global overview of the feature.&#x20;
   * Up to date documentation should be put here on SS3D's Gitbook.

### Check any linked issues

1. **Check any linked issues in the pull request.**&#x20;
   * If a PR links to an issue(s) to close them, check to make sure the PR meets the requirements of the issue. If for any reason parts of the issue cannot be met, make sure the reason is stated in the PR.

### Turn Known Issues into Github Issues

Not all issues need to be solved in a PR. On the contrary, sometimes it's better to avoid bloating it or delaying a merge. Known issues that can be kept are the one impacting only the newly added feature, not in a fatal way. It can be optimization issue, partial feature..

Turn all known acceptable issues into Github issues for someone to solve later on.

### All Good !&#x20;

**If you check all of these, accept the PR and warn a CentCom or a Maintainer member. If you're a CentCom or Maintainer member, you can merge the PR.**
