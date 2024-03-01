Solutions that are applied to test and production environments will be managed solutions. Solution architects need to be aware of the available options when importing managed solutions.

## Import managed solutions

We don't recommend that you create new solutions for each change or release of your application, which will lead to dependencies between components that will prevent you from importing the solution. Therefore, you should make changes to your solution(s) and then import the new version.

> [!NOTE]
> Solutions have version numbers. The version numbers are automatically incremented when you export a solution. You can't import a solution with a lower version number if the solution has already been imported with a higher version number.

When importing a new version of a managed solution, you should consider the following import options:

- **Update** - Applies the changes in the solution.
- **Upgrade** - Imports changes and applies them immediately, including removing components that are not in the new solution, the old solution, and any patches that are removed.
- **Stage for Upgrade** - Similar to upgrade, but it pauses after a new solution is imported before you have removed components so that you can do data migration. Then, you can manually trigger the final application of the solution.

Updates to a managed solution are deployed to the previous version of the managed solution. This action doesn't create an additional solution layer. You can't delete components by using an update.

Upgrading a solution installs a new solution layer immediately above the base layer. Solution upgrades will delete components that existed but are no longer included in the upgraded version.

Upgrade is the default option.

> [!IMPORTANT]
> Using the **Clone a patch** and **Clone solution** to update a solution is no longer recommended because it limits team development and increases complexity when you are storing your solution in a source control system.
