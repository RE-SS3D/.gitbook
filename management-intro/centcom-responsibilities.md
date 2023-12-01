# CentCom Responsibilities

## CentCom Member Responsibilities

There are 3 distinct areas of responsibility: designing, implementation, and management.

### Preface - Terms

Repositories - Place where code & assets are stored (e.g. GitHub).

Task - A piece of implementation work (i.e. coding a piece of a feature or making an asset).

Boards - the primary board is the GitHub implementation board, though we have other boards on Trello for asset todo tasks as well as a management board.

Wiki - Repository's Wiki (this has ben moved here to our gitbook but the term hasn't been updated throughout our documents fully yet).

Chat - The official place where communication takes place, in our case the Discord server.

### Responsibility - Designing

The team must collectively agree upon the features of the game before they can be implemented. Additionally, community opinion must be considered during design and designed features must be publicly viewable.

#### Process

1. An idea is placed into the design board's backlog and prioritized.
2. The most prioritized idea is put into in-design. A wiki document is made for it where members of the team start writing up the design.
   * Team members should not erase text without general agreement.
   * Documents should be in-design at least long enough for most of the team to contribute.
   * Controversial pieces should be open for community involvement and discussion so that they can influence the outcome. This could be done by vote or announcement in Chat.
3. Once the document is complete it is put into review, where any final problems are discussed.
   * Any existing problems can be mentioned in the wiki document, in a separate section.
   * \[optional] The community can vote (in Chat) on whether or not to accept the feature.
   * The review finishes when a majority vote passes on the decision.

#### Permissions & Tooling

The dev board must have columns for backlog, in design, in review, and complete. The wiki must have a section for writing feature designs. The chat must have a way for team members to create votes and announcements, and team members must be able to read and respond to community voices in the chat.

All team members have permission to read and modify the board and the wiki. The public has permission to read the board and wiki.

### Responsibility - Implementation

The team maintains the quality of the assets, the GitHub repositories, and maintains the boards both on GitHub and Trello. Additionally, team members can assign people to work on specific tasks.

Unlike designing, this responsibility is more individual - collective agreement is not required for many of the tasks.

#### Processes

* Team members (somewhat collectively) take designed features and turn them into tasks in the backlog.
* Team members (somewhat collectively) prioritize tasks in the 'backlog' and 'available' columns.
  * Available tasks are ones people can work on, backlog needs to be done but aren't meant to be worked on yet.
* Team members decide when to move the (top prioritized) tasks from 'backlog' to 'available'.
  * Tasks could be moved to ensure the available column has X amount of work in it.
* Any team member can assign an available task to _anyone_, and move the task to in-progress.
* Any team member can review a task that has been completed.

#### Permissions & Tooling

The implementation boards should indicate what tasks are available and unavailable to work on, in progress (and who is assigned to them), being reviewed, and what tasks are complete. Tasks that fail their review go back to being in-progress, tasks that pass their review should be immediately be placed in their respective repository. With GitHub, a lot of the above steps can be automated (e.g. accepted reviews being placed in the Done column). Additionally, GitHub can require PRs for tasks before merging.

Team members have permission to modify the boards, review and merge PRs to the repositories, as well as all public permissions. The public has permission to read the board and repositories, request to be assigned tasks, and submit PRs.

### Responsibility - Management

The team chooses collectively who is on the team. There can be some rules relating to promotion/demotion that are generally agreed on.

* When choosing to promote or demote someone, enough time must be given for most team members to voice their opinions.
* There could be an indiscriminate demotion for inactive members after 2+ months of no development (management or submissions) and/or 1 month of inactivity in chat. If a demoted member starts contributing again, they could be repromoted again through the same process as before.
