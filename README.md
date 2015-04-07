# Tasks

A simple way to plan tasks in a project.

## Taskfile

Just create a Taskfile in your project with the list of tasks that need to be done. For example:

    - Task A
    - Task B
    - Task C

You can mark tasks as finished by putting a cross:

    x Task A
    - Task B
    - Task C

This is not fun unless we add some modifiers to each task:

    x Task A. Do some stuff. Time: 1
    - Task B. Do other stuff. Time: 3. Progress: 1.
    - Task C. Do even more stuff. Time: 1. Before: Task B.

The `tasks` script will process this Taskfile and output what needs to be done for each day:

    $ tasks today
    Tuesday, 7 April 2015
        Task b

    $ tasks week
    Tuesday, 7 April 2015
        Task b
    Wednesday, 8 April 2015
        Task b
    Thursday, 9 April 2015
        Task c
    Total: 3 days

You can also just get a full calendar of all tasks (`tasks calendar`), get a graph of the different task dependencies (`tasks graph`, requires graphviz), get a list by worker (`tasks workers`), get a list of the tasks metadata (`tasks show`), or just get help (`tasks help`).

## Modifiers

Available modifiers in tasks:

* Time:      the amount of days a task will take.
* Load:      the amount of resources that will be dedicated to a task (min: 0, max: 1, default: 1).
* Progress:  the amount of days that have been dedicated to a task.
* Priority:  the priority a task has.
* By:        worker who will do the task.
* Before:    list of tasks that need to be done before.
* Deadline:  last date to perform the task.
* Not until: date before which the task cannot be started.
* On:        fixed date when the task will have to be done.

## Copyright

Copyright (c) 2015. MIT license, José Ignacio Fernández <`joseignacio.fernandez@gmail.com`>