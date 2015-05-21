## Sub-Processes and Linked Processes ##


[Back to Table of Contents](TableOfContents.md)


# Sub-Process #

  * In a logical sequence, sub process is a set of activities making up a small process.
  * Large processes are composed of sub processes, making implementation better and maintenance easier.

  * Here is a simple video that illustrates the use of sub processes:
https://www.youtube.com/watch?v=sR8lMd4MJ5Q&feature=player_embedded

  * Logically related steps can be encapsulated within parent process. No data mapping is needed in sub processes. They can directly access their parent process's business objects.

### Note ###
  * Sub processes are not reusable.
  * It can only be accessed and instantiated from the parent process.

  * Subprocess can be viewed as a single activity that provides simplified and high-level view of the parent process.

  * Subprocesses are mainly used basically for 2 reasons:

> (i) _Abstraction:_ To hide low-level implementation details. i.e, when the technical details are not important at the business level view of the process, those details can be put in the sub-process activity.

> (ii) _Modularization:_ To encapsulate steps that are repeated in the parent process into a single unit that can be re-used wherever necessary.

![http://i.imgur.com/piWEEaY.jpg](http://i.imgur.com/piWEEaY.jpg)


# Linked Process #

  * An activity can be implemented using linked processes.
  * Linked processes are also known as Nested Processes.

  * Linked process differ from subprocess because they can be accessed and instantiated from processes other than a single parent process.

  * Linked processes provide a way to encapsulate logically related steps within a process while retaining the high-level view of the parent process

  * Linked process activities are represented in the process diagram by an activity element with a thick border and an expandable subprocess marker

![http://i.imgur.com/t2PJlml.jpg](http://i.imgur.com/t2PJlml.jpg)

#### Another linked process Example ####
The steps for approving software request logged by an employee is to be performed by the team lead and also by the project manager.
So here, both the team lead and the manager perform same set of activities to approve the request. In this case, the approval steps can be made a linked process.

# Difference between sub-process and linked process #

![http://i.imgur.com/iXWQq9S.jpg](http://i.imgur.com/iXWQq9S.jpg)

### Tutorials ###
[Tutorial-SubProcess](TutorialSubprocesses.md)

[Tutorial-Linked Process](TutorialLinkedProcess.md)