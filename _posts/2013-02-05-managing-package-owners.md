---
ID: 148
post_title: Managing Package Owners on nuget.org
author: Jeff Handley
post_excerpt: ""
layout: post
permalink: >
  http://devblogs.microsoft.com/nuget/managing-package-owners/
published: true
post_date: 2013-02-05 00:00:00
---
While each NuGet package's [nuspec metadata][1] defines the package's owner(s), the NuGet gallery at nuget.org ignores that piece of nuspec metadata. Instead, ownership of a package is defined by who publishes the package to the gallery. Sometimes this metadata needs to be managed beyond the initial package publishing too, which means the owner metadata needs to be mutable while the package itself is not.

## Setting a Package's Initial Owner

When a brand new package is published to nuget.org, its initial owner is defined by the user that published the package.

1.  If the website's 'Upload Package' page was used to publish the package, then the logged-on user is the package's owner.
2.  If `nuget.exe push` was used to publish the package from the command-line, then the API key specified to nuget.exe will define the package's owner. This can be done by either including the API key in the [Push command][2], or by using the [SetApiKey command][3].

## Specifying Additional Package Owners

It's common for a package to have multiple developers; each developer can be listed as a co-owner of the package. Packages can also utilize a convention for "organizations" to indicate company/group ownership of a package. For example, the Microsoft ASP.NET packages are co-owned by [microsoft][4], [aspnet][5], and sometimes individuals on the feature team. The 'microsoft' and 'aspnet' accounts are simply set up with a mailing list email address that reaches the teams that manage the accounts.

Once a package has been published to nuget.org, it's easy to invite additional users to become owners of the package.

1.  [Log on][6] to nuget.org with the account that is the current owner of the package;
2.  Navigate to the package page using the 'Packages' tab, searching, or clicking your username to and then '[Manage My Packages][7]';
3.  When logged on as the package's owner, there is a 'Manage Owners' link on the left side to click;
4.  Enter the username of the person to add as an owner and click 'Add';
5.  An email is then sent to the new co-owner, as an invitation to become an owner of the package;
6.  Once that user clicks the link, they are a full co-owner with full control over the package, including the ability to remove other users as owners.

Until the new owner confirms ownership, they *will not* be listed as an owner of the package. When viewing the 'Manage Owners' page, you will see a "pending approval" entry in the current owners. That invitation can be removed, just as other owners can be removed.

This process of invitations prevents users from falsely adding other users as owners of their packages. Note that the "Authors" metadata is purely freeform text; only "Owners" are controlled.

## Removing Package Owners

All package owners are peers. This means any package owner can publish a new version of the package. It also means that any package owner can remove any other package owner. No owner has more authority than other owners.

When a package has multiple owners and one needs to be removed the process is simple:

1.  [Log on][6] to nuget.org with the account that is the current owner of the package;
2.  Navigate to the package page using the Packages tab, searching, or clicking your username to and then '[Manage My Packages][7]';
3.  When logged on as the package's owner, there is a 'Manage Owners' link on the left side to click;
4.  Click the 'remove' link next to the owner to be removed.

## Transfering Package Ownership

We sometimes get support requests to transfer package ownership from one user to another, but you can almost always accomplish this yourself. Transfering ownership from one user to another is simply a combination of the two features above.

1.  The current owner invites the new user to become a co-owner and the new user accepts the invite;
2.  The new user removes the old user from the list of owners.

This request has come in under a couple forms but the process works the same.

*   The package ownership is changing from one developer to another
*   The package was accidentally published using the wrong account

## Orphaned Packages

One last scenario has occurred, but not many times. Packages have become orphans and the only package owner account cannot be used to add new owners. Here are some examples of this scenario:

*   The owner's account is associated with an email address that no longer exists and the user has forgotten their password
*   The registered owner has left the company that produces the package and cannot be reached to update the package ownership
*   Due to a bug that has only affected a handful of packages, the package is somehow ownerless on the gallery

Some members of the NuGet team are in the 'admin' role on the gallery and can access the 'Manage Owners' link for any package. If you are the rightful owner of a package and cannot reach the current owner to gain ownership permissions, then use the 'Report Abuse' link on the gallery to reach the NuGet team. We will then follow a process to verify your ownership of the package. If we determine you should be an owner of the package, we will use the 'Manage Owners' link for the package ourselves and send you the invite to become an owner. We will only do this after verifying that you should be an owner and the process for this varies by circumstances. Often times, we will use the package's Project URL to find a way to contact the project owner, but we may also use Twitter, Email, or other means for contacting the project owner.

 [1]: http://docs.nuget.org/docs/reference/nuspec-reference
 [2]: http://docs.nuget.org/docs/reference/command-line-reference#Push_Command
 [3]: http://docs.nuget.org/docs/reference/command-line-reference#Setapikey_Command
 [4]: http://nuget.org/profiles/microsoft
 [5]: http://nuget.org/profiles/aspnet
 [6]: https://nuget.org/users/account/LogOn
 [7]: https://nuget.org/account/Packages