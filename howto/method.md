# Work method

For prototyping improvements, we are currently experimenting a custom iterative workflow inspired from Agile methods.

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
