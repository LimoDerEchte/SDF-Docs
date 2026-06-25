# Getting Started

## Creating the Mods Folder
To create a mod using SDF, create a folder with your mods name in the ue4ss `Mods` directory.

Inside of this mod, create a structure that looks like this:

```
Mods/ExampleMod
├── enabled.txt
├── SDF
│   ├── content.toml
│   ├── other_content.toml
│   └── SomeFolder
│       └── content_in_folder.toml
```

## Adding Content
> If you are new to SDF modding, you might want to have a look at the [examples](examples.md)

SDF will automatically scan for any enabled mods containing an SDF folder at launch. It will then recursively go through every SDF folder and find every .toml file that contains any SDF content. You can find more about the required syntax for said content in the following sections of this wiki:

| Page                                                       | Content                                             |
|------------------------------------------------------------|-----------------------------------------------------|
| [Crafting Recipes](../data/recipes.md)                     | Create, modify or delete crafting recipes           |
| [Crafting Recipe Categories](../data/recipe_categories.md) | Create, modify or delete crafting recipe categories |
