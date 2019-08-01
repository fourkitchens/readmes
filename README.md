# Four Kitchen General Purpose Readme Sections

This respository houses the basic layout of readmes on a 4K project. One can use this framework and the following examples to *build* readmes in their project using node so that the documentation only has to be updated in a single place.

## Repository Structure

The structure of this repository is roughly layed out in [Hosting]/[Framework]/[Build Type].

**Hosting** is they type of hosting. It consists of typically Pantheon, Acquia, and Custom.

**Framework** is the type of project. Example, D7, D8, or Wordpress.

**Build Type** is based on the build architecture. Typically this is identified as something like Composer, Aquifer, Drush Make, or Manual.

It is possible for a Hosting/Framework/Build Type combination to share documentation between each. In those situations, simply place it in the most common denomination of commonality like [Hosting]/[Framework] or [Hosting]. In other cases, symlink to the correct documentation piece.

If documentation applies to all instances, feel free to add it to the `global` folder at the hosting level.

## How To Use

In your existing project, you will need to add an .emdaer.yml file. You will also need to add emdaer and this readmes document as a dependency. You can then run emdaer as a command any time you wish to update your documentation. An example follows.

### package.json
```
{
  "name": "emdaer-test",
  "description": "",
  "scripts": {
    "emdaer": "emdaer"
  },
  "devDependencies": {
    "emdaer": "^0.3.3",
    "readmes": "git+ssh://git@github.com:fourkitchens/readmes.git"
  }
}
```

### .emdaer.yml
```
- text: '# Manual Pantheon Project'
- text: "This is a brief overview of my manual Pantheon Project located at https://github.com/fourkitchens/readmes/tree/master/pantheon/d7/manual"
- include: './node_modules/readmes/pantheon/d7/manual/at-a-glance.md'
- include: './node_modules/readmes/pantheon/d7/manual/brief-foundation-architecture.md'
- include: './node_modules/readmes/pantheon/d7/manual/before-you-start.md'
- include: './node_modules/readmes/pantheon/d7/manual/getting-started.md'
- include: './node_modules/readmes/pantheon/d7/manual/subsequent-builds.md'
- include: './node_modules/readmes/pantheon/d7/manual/git-workflow.md'
- include: './node_modules/readmes/pantheon/d7/manual/configuration-management-workflow.md'
- include: './node_modules/readmes/pantheon/d7/manual/deployment.md'
- include: './node_modules/readmes/pantheon/d7/manual/testing.md'
- include: './node_modules/readmes/pantheon/d7/manual/known-issues.md'
```

### Edits:
If you need custom edits to your readme, create a docs directory and change `node_modules/readmes/pantheon/d7/manual` to `docs` in the `.emdaer.yml` file.

Run:
```
npm install
npm run emdaer
```
You will have a rendered version of the Manual Pantheon Project. You can see this example in https://github.com/fourkitchens/readmes/tree/master/examples/pantheon-d7-manual.
