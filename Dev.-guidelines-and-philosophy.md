Being a project of a certain level of difficulty and of a certain size,<br/>
these are some points to take into account for the development,<br/>
by adopting this good practices it will be easier to deal with the growth of this project.

Please note that if you decide to contribute it means that you automatically accept the licensing conditions (MIT license) of this project.

**Readability of the code**

The [PEP8](https://www.python.org/dev/peps/pep-0008/) rules are followed in this project, source code editors like PyCharm if correctly configured, helps to check and report typing errors without having to learn all the rules and it is possible to take inspiration from existing source code.

**Unit and integration testing**

This brings reliability in the written code, therefore every new change to the code must pass the tests (tests are performed each time a Pull Request will be modified)

**When possible drop as many external libraries**

When possible, integrate functionality using native python functions without requiring an additional external module.
An example is the 'urllib3' or 'requests' library, on slower devices take a long time to load them,
similarly also importing external addons may cause slowdowns.

**Some rules for import modules**

Most of the time it has been chosen to use imports at top level instead to place them inside funtions.

A simple example of what it means to use import at top level or inside a function:
[Import Statement Overhead](https://wiki.python.org/moin/PythonSpeed/PerformanceTips#Import_Statement_Overhead)

Using import at top level, has advantages and disadvantages:
- More readable and easier to maintain code essential in large projects
- Can slow down the execution of code on slower devices (e.g. RPI)

Where and when the two import modes are used:
- In the entry points files (and other particular related files e.g. db_update.py) are used imports inside functions to speedup startup time
- In global.py are used imports inside functions to speedup startup time and avoid problems with circular imports
- In the remaining project in general are used imports at top level to make it easier to maintain and read the source code

**License and copyright**

This information are included in each python file,
the license information follows the [SPDX](https://spdx.org/ids) standard,
in addition the copyright and a possible module title are included together,
then for each new file these informations must be included.

The copyright info included are of two levels, at project level and the user who implements the module.
The format is as follows:
<pre>
"""
    Copyright (C) 2017 Sebastian Golasch (plugin.video.netflix)
    Copyright (C) 2018 Author Name (original implementation module)
    The best title for this beautiful module

    SPDX-License-Identifier: MIT
    See LICENSES/MIT.md for more information.
"""
</pre>

When you modify an existing module very heavily it is advisable to add also your copyright to the existing ones

**Code readability over cleverness**

Transparency is key if we want outsiders to help improve this project

**And last but not least**

Simple tips for the pythonist [The Zen of Python](https://www.python.org/dev/peps/pep-0020/) 🧐🎉✨


Thanks to Dag Wieers/plugin.video.vrt.nu for the scheme