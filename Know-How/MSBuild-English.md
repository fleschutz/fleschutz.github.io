![Bild](/img/BannerCleanup.jpg)

(Foto: pixabay.com)

Introduction to MSBuild
=======

***MSBuild* is a free and open-source build tool from Microsoft that helps automate the process of creating a software product, including compiling the source code, packaging, testing, deployment and creating documentations.**

... ![Bild](/img/MF.png) *By Markus Fleschutz* 🕓 *April 6, 2018*

The *MSBuild* release version is v15.0 provided by Visual Studio 2017 and v16.0 provided by Visual Studio VS2019. It's licensed under the MIT license.

*MSBuild* is based on **XML** files: projects typically have a solution file (suffix **.sln**, which include dependancies) and a project file (suffix **.vcxproj**). The XML format is based on: properties (key-value pairs), items (list of things, typically files) with metadata, targets and tasks

## Target

A **Target** contains a set of tasks for *MSBuild* to execute. The focus of *MSBuild* is the result *Target* specified when invoking *MSBuild* with the project file. This is because a *Project* may contain several *Target* entries, each executed sequentially (and conditionally). Subsequent dependent Targets are executed before the requested Target. The execution flow of the current *Target* can be directed using the following attributes: Condition, BeforeTargets, AfterTargets, & DependsOnTargets. Each Target may be self-contained with the necessary Tasks to complete itself. A Target is typically an action executed on a file, set of files or directory.

## Task

A **Task** is a command which is executed in order to complete a Target. *Tasks* are used to group and execute any number of actions during the build process. They are typically implemented in a .NET assembly as a class which inherits from the Task class or implements the ITask interface. Many basic tasks are shipped as part of the .NET Framework and community developed tasks are freely available. Some examples of *Tasks* include copying files, creating directories, or parsing XML.

*MSBuild* provides **Properties** and **Items**, which are conceptually equivalent to make's macros. Properties specify static values, whereas Items are usually used to define sets of files or folders on which to perform Tasks. Specifying files on Items is made easy by the support of wildcards.

Web Links
---------

*  [wikipedia.org/MSBuild](https://en.wikipedia.org/wiki/MSBuild) - MSBuild on Wikipedia
*  [docs.microsoft.com](https://docs.microsoft.com/de-de/visualstudio/msbuild/msbuild?view=vs-2019) - MSBuild on Microsoft Docs
*  [github.com/microsoft/msbuild](https://github.com/microsoft/msbuild) - the MSBuild project on GitHub
