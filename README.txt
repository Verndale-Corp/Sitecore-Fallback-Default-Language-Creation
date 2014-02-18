Verndale Adding Language Versions by Default in Sitecore

Purpose
Make it easier to ensure all language versions are added for items, both on creation, or via an explicit ribbon command.

Compatibility
This assumes you are using the latest version of the Partial Language Fallback Module
http://marketplace.sitecore.net/en/Modules/Language_Fallback.aspx

How to build code and deploy the solution
1. When using the fallback module, make sure to compile the source code to get the dll, do not use the one within the package.

2. Download and unzip the Verndale.SharedSource.zip from this repository, it contains a class library
3. The important files in this are CreateVersionInAllLanguagesOnCreate.cs, CreateVersionInAllLanguages.cs, LanguageHelper.cs

4. Download the App_Config folder, there are necessary updates within Sitecore.SharedSource.PartialLanguageFallback.config.example
You can use the whole thing or take the parts from it that you need and add to your fallback.config
It includes an item:created event so that all language versions will be added for an item being created in a path with a new setting (Fallback.PathsToCheckForLanguageVersions)
There is also an update in Commands.config which will add a new command which will be installed in below sitecore package

5. Download and install the Fallback Default Language Creation-1.zip Sitecore package
It includes a core item for adding the Add All Language Versions command to the ribbon

Testing
1. Update the Fallback.PathsToCheckForLanguageVersions in the fallback.config to a path in your sitecore content tree
2. Add a new content item within that path in the sitecore content tree
3. See that all languages in the system have been added as well as the one you explicitly added
4. For an item that already exists that is missing a language version, click it and then click the Add All Language command button in the Versions tab, see that it all language version now exist

Review the blog series about Partial Language Fallback on Sitecore, link TBD
