---
ID: 225971
post_title: NuGet 2.7 Release Candidate Available
author: seroha
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/nuget-2-7-release-candidate-available/
published: true
post_date: 2013-08-14 00:00:00
---
The NuGet 2.7 Release Candidate is now available, with an expected release before the end of August.

*   [Download: Visual Studio Extensions and NuGet.exe Command-Line][1]
*   [All Work Items for the Release][2]
*   [Open Issues][3]
*   [Work Items Being Tested][4]

If you encounter any problems with NuGet 2.7, especially any regressions, please file an issue on [CodePlex][5] right away and prefix the issue with "[NuGet 2.7]".

Please note that we plan to include NuGet 2.7 in the final release of Visual Studio 2013, so the features and bug fixes in this release will be available in-the-box for all Visual Studio 2013 users.

## Acknowledgements

We would like to thank the following external contributors for their significant contributions to NuGet 2.7:

1.  [Mike Roth][6] ([@mxrss][7]) 
    *   Show License url when listing packages and verbosity is detailed.
2.  [Adam Ralph][8] ([@adamralph][9]) 
    *   [#1956][10] - Add developmentDependency attribute to packages.config and use it in pack command to only include runtime packages
3.  [Rafael Nicoletti][11] ([@tkrafael][12]) 
    *   Avoid duplicate Properties key in nuget.exe pack command.
4.  [Ben Phegan][13] ([@BenPhegan][14]) 
    *   [#2610][15] - Increase machine cache size to 200.
5.  [Slava Trenogin][16] ([@derigel][17]) 
    *   [#3217][18] - Fix NuGet dialog showing updates in the wrong tab
    *   Fix Project.TargetFramework can be null in ProjectManager
    *   [#3248][19] - Fix SharedPackageRepository FindPackage/FindPackagesById will fail on non-existent packageId
6.  [Kevin Boyle][20] ([@kevfromireland][21]) 
    *   [#3234][22] - Enable support for Nomad project
7.  [Corin Blaikie][23] ([@corinblaikie][24]) 
    *   [#3252][25] - Fix push command fails with exit code 0 when file doesn't exist.
8.  [Martin Veselý][26] 
    *   [#3226][27] - Fix bug with Add-BindingRedirect command when a project references a database project.
9.  [Miroslav Bajtos][28] ([@bajtos][29]) 
    *   [#2891][30] - Fix bug of nuget.pack parsing wildcard in the 'exclude' attribute incorrectly.
10. [Justin Dearing][31] ([@zippy1981][32]) 
    *   [#3307][33] - Fix bug NuGet.targets does not pass $(Platform) to nuget.exe when restoring packages.
11. [Brian Federici][34] ([@benerdin][35]) 
    *   [#3294][36] - Fix bug in nuget.exe package command which would allow adding files with the same name but different casing, eventually causing "Item already exists" exception.
12. [Daniel Cazzulino][37] ([@kzu][38]) 
    *   [#2990][39] - Add Version property to NetPortableProfile class.
13. [David Simner][40] 
    *   [#3460][41] - Fix bug NullReferenceException if requireApiKey = true, but the header X-NUGET-APIKEY isn't present
14. [Michael Friis][42] ([@friism][43]) 
    *   [#3278][44] - Fixes NuGet.Build targets file to so that it works correctly on MonoDevelop

## Notable features in the release

### Package Restore by Default (with implicit consent)

NuGet 2.7 introduces a new approach to package restore, and also overcomes a major hurdle: Package restore consent is now on by default! The combination of the new approach and the implicit consent will drastically simplify package restore scenarios.

#### Implicit Consent

With NuGet versions 2.0, 2.1, 2.2, 2.5, and 2.6, users needed to explicitly allow NuGet to download missing packages during build. If this consent had not been explicitly given, then solutions that had enabled package restore would fail to build until the user had granted consent.

Starting with NuGet 2.7, package restore consent is ON by default while allowing users to explicitly *opt out* of package restore if desired, using the checkbox in NuGet's settings in Visual Studio. This change for implicit consent affects NuGet in the following environments:

*   Visual Studio 2013 Preview
*   Visual Studio 2012
*   Visual Studio 2010
*   NuGet.exe Command-Line Utility

#### Automatic Package Restore in Visual Studio

Starting with NuGet 2.7, NuGet will automatically download missing packages during build in Visual Studio, even if package restore hasn't been explicitly enabled for the solution. This automatic package restore happens in Visual Studio when you build a project or the solution, but before MSBuild is invoked. This yields a few significant benefits:

1.  No further need to use the "Enable NuGet Package Restore" gesture on your solution
2.  Projects don't need to be modified, and NuGet won't make changes to your project to ensure package restore is enabled
3.  All NuGet packages, including those that included MSBuild imports for props/targets files, will be restored *before* MSBuild is invoked, ensuring those props/targets are properly recognized during the build

In order to use Automatic Package Restore in Visual Studio, you only need to take one (in)action:

1.  Don't check in your `packages` folder

While all users are implicitly opted into automatic package restore, you can easily opt out through the Package Manager settings in Visual Studio.

![Package Manager Settings][45]

#### Simplified Package Restore from the Command-Line

NuGet 2.7 introduces a new feature for nuget.exe: `nuget.exe restore`

This new Restore command allows you to easily restore all packages for a solution with a single command, by accepting a solution file or folder as an argument. Furthermore, that argument is implied when there's only a single solution in the current folder. That means the following all work from a folder that contains a single solution file (MySolution.sln):

1.  nuget.exe restore MySolution.sln
2.  nuget.exe restore .
3.  nuget.exe restore

The Restore command will open the solution file and find all projects within the solution. From there, it will find the packages.config files for each of the projects and restore all of the packages found. It also restores solution-level packages found in the .nugetpackages.config file. More information about the new Restore command can be found in the [Command-Line Reference][46].

#### The New Package Restore Workflow

We are excited about these changes to Package Restore, as it introduces a new workflow. If you want to omit your packages from source control you simply don't commit the `packages` folder. Visual Studio users who open and build the solution will see the packages automatically restored. For command-line builds, simply invoke `nuget.exe restore` before invoking `msbuild`. You'll no longer need to remember to use the "Enable NuGet Package Restore" gesture on your solution, and we'll no longer need to modify your projects to alter the build. And this also yields a much improved experience for packages that include MSBuild imports, especially for imports added through NuGet's recent feature for [automatically importing props/targets files][47] from the build folder.

In addition to the work we've done ourselves, we're also working with some important partners to round this new approach out. We don't have concrete timelines for any of these yet, but each partner is as excited as we are about the new approach.

*   Team Foundation Service - They are working to integrate the call to `nuget.exe restore` into the default build scenarios.
*   Windows Azure Web Sites - They are working to allow you to push your project to Azure and have `nuget.exe restore` called before your web site is built.
*   TeamCity - They are updating their NuGet Installer plugin for TeamCity 8.x
*   AppHarbor - They are working to allow you to push your repo to AppHarbor and have `nuget.exe restore` called before your solution is build.

With each of the partners above, they would use their own copy of nuget.exe and you would not need to carry nuget.exe in your solution.

### Project Retargeting and Upgrade Build Errors/Warnings

Many times after retargeting or upgrading your project, you find that some NuGet packages aren't functioning properly. Unfortunately, there is no indication of this and then there's no guidance on how to address it. With NuGet 2.7, we now use some Visual Studio events to recognize when you've retargeted or upgraded your project in a way that affects your installed NuGet packages.

If we detect that any of your packages were affected by the retargeting or upgrade, we'll produce immediate build errors to let you know. In addition to the immediate build error, we also persist a `requireReinstallation="true"` flag in your packages.config file for all packages that were affected by the retargeting, and each subsequent build in Visual Studio will raise a build warnings for those packages.

While NuGet cannot take automatic action to reinstall affected packages, we hope this indication and warning will guide help you discover when you need to reinstall packages. We are also working on [package reinstallation guidance documentation][48] that these error messages direct you to.

### NuGet Configuration Defaults

Many companies are using NuGet internally, but have had a hard time guiding their developers to use internal package sources instead of nuget.org. NuGet 2.7 introduces a Configuration Defaults feature that allows machine-wide defaults to be specified for:

1.  Enabled package sources
2.  Registered, but disabled package sources
3.  The default nuget.exe push source

Each of these can now be configured within a file located at %ProgramData%NuGetNuGetDefaults.config. If this config file specifies package sources, then the default nuget.org package source will not be registered automatically, and the ones in NuGetDefaults.config will be registered instead.

While not required to use this feature, we expect companies to deploy NuGetDefaults.config files using Group Policy.

*Note that this feature will never cause a package source to be removed from a developer's NuGet settings. That means if the developer has already used NuGet and therefore has the nuget.org package source registered, it won't be removed after the creation of a NuGetDefaults.config file.*

See [NuGet Configuration Defaults][49] for more information about this feature.

### Renaming the Default Package Source

NuGet has always registered a default package source called "NuGet official package source" that points to nuget.org. That name was verbose and it also didn't specify where it was actually pointing. To address those two issues, we've renamed this package source to simply "nuget.org" in the UI. The URL for the package source was also changed to include the "www." prefix. After using NuGet 2.7, your existing "NuGet official package source" will automatically be updated to "nuget.org" as its name and "<https://www.nuget.org/api/v2/>" as its URL.

### Performance Improvements

We made some performance improvement in 2.7 which will yield smaller memory footprint, less disk usage and faster package installation. We also made smarter queries to OData-based feeds which will reduce the overall payload.

### New Extensibility APIs

We added some new APIs to our extensibility services to fill the gap of missing functionalities in previous releases.

#### IVsPackageInstallerServices

     // Checks if a NuGet package with the specified Id and version is installed in the specified project. 
    bool IsPackageInstalledEx(Project project, string id, string versionString); 
    
    // Get the list of NuGet packages installed in the specified project. 
    IEnumerable<IVsPackageMetadata> GetInstalledPackages(Project project);
    

#### IVsPackageInstaller

     // Installs one or more packages that exist on disk in a folder defined in the registry. 
    void InstallPackagesFromRegistryRepository(string keyName, bool isPreUnzipped, bool skipAssemblyReferences, Project project, IDictionary<string, string> packageVersions); 
    
    // Installs one or more packages that are embedded in a Visual Studio Extension Package. 
    void InstallPackagesFromVSExtensionRepository(string extensionId, bool isPreUnzipped, bool skipAssemblyReferences, Project project, IDictionary<string, string> packageVersions);
    

### Development-Only Dependencies

This feature was contributed by [Adam Ralph][9] and it allows package authors to declare dependencies that were only used at development time and don't require package dependencies. By adding a `developmentDependency="true"` attribute to a package in packages.config, nuget.exe pack will no longer include that package as a dependency.

### Removed Support for Visual Studio 2010 Express for Windows Phone

The new package restore model in 2.7 is implemented by a new VSPackage which is different from the main NuGet VSPackage. Due to a technical issue, this new VSPackage doesn’t work correctly in the Visual Studio 2010 Express for Windows Phone SKU as we share the same code base with other supported Visual Studio SKUs. Therefore, starting with NuGet 2.7, we are dropping support for Visual Studio 2010 Express for Windows Phone from the published extension.

Since we are unsure how many developers are still using NuGet in that version/edition of Visual Studio, we are publishing a separate Visual Studio extension specifically for those users and publishing it on CodePlex (rather than the Visual Studio Extension Gallery). We don't plan to continue to maintain that extension, but if this affects you please let us know by filing an issue on CodePlex.

To download the NuGet Package Manager (for Visual Studio 2010 Express for Windows Phone), visit the [NuGet 2.7 Downloads][1] page.

### Bug Fixes

In addition to these features, this release of NuGet also includes many other bug fixes. There were 97 total issues addressed in the release. For a full list of work items fixed in NuGet 2.7, please view the [NuGet Issue Tracker for this release][2].

 [1]: https://nuget.codeplex.com/releases/view/107605
 [2]: https://nuget.codeplex.com/workitem/list/advanced?release=NuGet%202.7&status=all
 [3]: https://nuget.codeplex.com/workitem/list/advanced?keyword=&status=Proposed|Active&release=NuGet%202.7
 [4]: https://nuget.codeplex.com/workitem/list/advanced?keyword=&status=Resolved&release=NuGet%202.7
 [5]: http://nuget.codeplex.com
 [6]: http://www.codeplex.com/site/users/view/mxrss
 [7]: https://twitter.com/mxrss
 [8]: http://www.codeplex.com/site/users/view/adamralph
 [9]: https://twitter.com/adamralph
 [10]: http://nuget.codeplex.com/workitem/1956
 [11]: http://www.codeplex.com/site/users/view/tkrafael
 [12]: https://twitter.com/tkrafael
 [13]: http://www.codeplex.com/site/users/view/benphegan
 [14]: https://twitter.com/benphegan
 [15]: http://nuget.codeplex.com/workitem/2610
 [16]: http://www.codeplex.com/site/users/view/derigel
 [17]: https://twitter.com/derigel
 [18]: http://nuget.codeplex.com/workitem/3217
 [19]: http://nuget.codeplex.com/workitem/3248
 [20]: http://www.codeplex.com/site/users/view/KevinBoyleRG
 [21]: https://twitter.com/kevfromireland
 [22]: http://nuget.codeplex.com/workitem/3234
 [23]: http://www.codeplex.com/site/users/view/corinblaikie
 [24]: https://twitter.com/corinblaikie
 [25]: http://nuget.codeplex.com/workitem/3252
 [26]: http://www.codeplex.com/site/users/view/veselkamartin
 [27]: http://nuget.codeplex.com/workitem/3226
 [28]: http://www.codeplex.com/site/users/view/miroslavbajtos
 [29]: https://twitter.com/bajtos
 [30]: http://nuget.codeplex.com/workitem/2891
 [31]: http://www.codeplex.com/site/users/view/zippy1981
 [32]: https://twitter.com/zippy1981
 [33]: http://nuget.codeplex.com/workitem/3307
 [34]: http://www.codeplex.com/site/users/view/benerdin
 [35]: https://twitter.com/benerdin
 [36]: http://nuget.codeplex.com/workitem/3294
 [37]: http://www.codeplex.com/site/users/view/dcazzulino
 [38]: https://twitter.com/kzu
 [39]: http://nuget.codeplex.com/workitem/2990
 [40]: https://www.codeplex.com/site/users/view/DavidSimner
 [41]: https://nuget.codeplex.com/workitem/3460
 [42]: https://www.codeplex.com/site/users/view/friism
 [43]: https://twitter.com/friism
 [44]: https://nuget.codeplex.com/workitem/3278
 [45]: https://devblogs.microsoft.com/nuget/wp-content/uploads/sites/49/2019/05/package-manager-settings.png
 [46]: http://docs.nuget.org/docs/reference/command-line-reference#Restore_Command
 [47]: http://docs.nuget.org/docs/release-notes/nuget-2.5#Automatic_import_of_msbuild_targets_and_props_files
 [48]: http://docs.nuget.org/docs/workflows/reinstalling-packages
 [49]: http://docs.nuget.org/docs/reference/nuget-config-defaults