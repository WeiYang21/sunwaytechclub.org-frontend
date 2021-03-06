# Contribute to Sunway Tech Club website 😋

## 📝 Table of Contents

- [Branching Strategy](#branching)
- [Commit message practices](#commit-message)
- [Folder structure practices](#file-structure)
- [Creating global components](#global-components)

## 🌿 Branching Strategy <a name="branching"></a>

For branching strategy we follow the following prefix:

- Feature: `Feature/<your feature>`

  - Basically the page you are working on

- Issue: `Issue/<your issue>`

  - The heavy bug that you are trying to solve

After you had an open pull request, you will need to have at least 1 reviewer to approve your pull request!

## ☹ Commit message practices <a name="commit-message"></a>

> How to Write a Git Commit Message - [https://chris.beams.io/posts/git-commit/](https://chris.beams.io/posts/git-commit/)

To let the future contributors be able to read our commit messages, it's important to follow below conventions:

- First-line start with a capital letter and no period at the end.
- Use present tense ( no `updated`, `added` )
- Common keyword to start:
  - `Update...`
  - `Refactor...`
  - `Create...`
  - `Add...`
- Use `Housekeeping` if fix typo, delete comments, etc

## 📁 Folder structure practices <a name="file-structure"></a>

To let future contributors be easier to contribute, it's important to settle on the scalable file structure, as we can foresee this will slowly becoming a big application.

Generally, the skeleton of the project will have the following file structure:

```folder
src
|_components
|_units
|_config
|_utils
|_App.svelte
|_main.js
|_rootRoutes.js
```

- Components - All your global components
- Units - All your other units' folder e.g. profile, event, marketplace...
- Config - All your custom configuration e.g. database.js, color.js, etc...
- Utils - All global utils
- App.svelte - Main app
- main.js - Main script
- rootRoutes.js - Root routes of the app

### Unit folder strucuture

A unit folder structure should be as below with examples:

```folder
units
|_event
| |_components
| |_units
| |_config
| |_utils
| |_Index.svelte
| |_services.js
| |_routes.js
|_<other units>
```

- Components - Your unit-specific components
- Units - Your unit-specific child units
- Config - Your unit-specific config folder
- Utils - Your unit-specific utils
- Index.svelte - Main app for this unit
- services.js - Your logic of the unit, including calling REST endpoints, etc. Separating logic from the view.
- routes.js - Routing for this unit

As you can see, it's a recursive pattern that can scale.

Compared with typical `components, pages` structure, this way it makes the frontend app more scalable.

## 🧱 Creating global components <a name="global-components"></a>

A global components are components those will be shared among all the units, example be `button`, `navbar`, etc.

To create a global component, simply create it under `/src/components`

There is only 1 practice, try to keep the usage as close to how we will be using a native HTML tag, an example has shown below:

Scenario: creating a text input

1. Create a component called `TextInput.svelte`
2. Utilize Sveltejs `$$restProp` and `slot` features
  
    - 2.0 Perform any styling as you want
    - 2.1 `<input {...$$restProp}/>`

        - `$$restProp` are the extra props that passed down, in this case all the extra props will be passed into the actual `<input>` tag.

Just a rule on thumb, try to make it as flexible to suit any situation as possible, try not to hard-code it.

And that's it! Happy coding 😋
