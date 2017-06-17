# Work method

For medicotechnical improvements, we are currently experimenting a custom iterative workflow inspired from Agile methods.

The main technical constrains and specifications of the device and app are listed in the [product backlog](../backlog/backlog.md). The latter has been written in tandem with physicians, in order to determine the configuration that best suits their needs. It might however change in time, especially to gradually take into account the requirements that must be fulfilled for medical certification.

The technical and software improvements are performed in an iterative workflow. Each iteration ends with a fully documented stable release of a functional version of the device, together with a version of the app that allows to display the images \(and, in the future, is intended for interacting with the device to set some parameters\).

## Organization

Different teams gather contributors according to their skills and fields of expertise. Obviously, one contributor can choose to be part of several teams.

Each team has its own repo on the [echOpen GitHub](https://github.com/echopen), as well as a dedicated channel on the [echOpen Slack](http://slack.echopen.org/). Most of the teams have weekly meetings, physically hosted at Hôtel Dieu, but it's also possible to attend remotely. The minutes of meetings are available in the Follow-up section of this gitbook. Each team designates at least one team maintainer, who is in charge of the GitHub repo. The team maintainer is not necessarily permanent, the designation may change in time.

A weekly follow-up takes place at Hôtel Dieu every Monday at 7:00pm. This meeting allows a transverse management of the project. At least one member of each team may attend. The team representative is not necessarily the team maintainer.

To know more about existing teams and how to reach them, jump to [Find your team](teams.md).

## Iteration workflow

Each iteration runs for several months and is segmented as follows:

* A CapTech is organized. It's a one-day meeting gathering medicotechnical contributors as well as external advisors who are experts in relevant fields \(electronics, mechanics...\). Given the achievements of the latest release, the next requirements to address are determined. These ones are translated in terms of technical specifications and UX design. 
* An iteration planning is derived from the decisions taken during the CapTech. Precise tasks to be fulfilled within the iteration are determined and assigned to each corresponding team. 
* The "make" phase runs for several weeks and lets contributors complete some tasks of the iteration planning. This phase is considered finished when a stable version of the prototype \(device + app\) is achieved.
* The "test" phase allows to characterize the prototype in a technical point of view.
* A full documentation of the release is realized, as well as a production guide describing the detailed steps  needed to reproduce the prototype and install the mobile app.

# Medicotechnical gitbook

## Purpose

This gitbook is the medicotechnical teams' main information medium. It gathers in a single place long term objectives, the latest stable release, a track record of former versions, the work in progress, and needs for contributions.

## Outline

* **Product backlog** : summary of the long-term objectives
* **Challenges** : punctual challenges to which everyone \(not only team members\) can participate
* **In progress** : information and follow-up of ongoing iteration
* **Stable release Vx.y.z** : information about the latest stable release \(specifications, documentation, realisation guide\)
* **Follow-up** : Minutes of weekly meetings
* **References** : Shared bibliography and references

# GitHub

All the medicotechnical contributions are done through the [echOpen GitHub](https://github.com/echopen).

## Structure

Each team has its own [repository](https://github.com/echopen). We use [GitHub teams](https://github.com/orgs/echopen/teams) to materialize the relationship between team members and handle access rights to our repositories. Each team has at least one maintainer \(or owner\) who is in charge of the corresponding repo.

We use [GitHub project boards](https://help.github.com/articles/about-project-boards/) to manage the ongoing tasks within the [iteration planning](../inprogress/planning.md). Each team has several project boards allowing its members to get an overview of the state of progress, and to assign themselves some tasks.

## Contribution guide

To become a contributor, start by creating your own [GitHub account](https://github.com/join).

* Explore our [team list](https://github.com/orgs/echopen/teams) and **subscribe** to the one\(s\) that you would like to integrate
* Fork the team's repo  
  To know more about forking on GitHub, jump to the [help page](https://help.github.com/articles/fork-a-repo/).

* Explore the team's project boards. Needs for contribution correspond to cards that are in the "To Do" or "Top Priority" lists.

* To contribute to some tasks, assign yourself the corresponding issue and move the card to "In Progress". Assignement to tasks is not exclusive. If you're interested in helping on some task already assigned to a contributor, just assign yourself the task as well and write a comment on the corresponding issue to get in touch with your co-workers. **For the sake of project management, please only assign yourself tasks that you will actually work on!**
* Once the task is complete, check that your contribution fulfills the "closing criteria" that are detailed in the corresponding issue.
* Make a pull request referencing the issue   
  To know more about pull requests on GitHub, jump to the [help page](https://help.github.com/articles/about-pull-requests/).

* Move the card to "Done". You're done !



