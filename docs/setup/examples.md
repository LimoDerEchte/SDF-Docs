# Examples

## Crafting Recipe Root Category
This is a category that will appear at the root of the fabricator UI.
<br>[➔ _Learn More_](../data/recipe_categories.md)
```toml
[[category]]
id = "ExampleModRootCategory"
name = "Example Mod Root Category"
icon = "ITEM Titanium" # This statement will use the icon of titanium for the category

crafted_by = "Fabricator" # This statement is required for SDF
ordering_index = 100 # The ordering index is used to decide the index the category appears at
```

## Crafting Recipe Category
This is a category that will appear inside the previously declared root category.
<br>[➔ _Learn More_](../data/recipe_categories.md)
```toml
[[category]]
id = "ExampleModCategory"
name = "Example Mod Category"

crafted_by = "Fabricator"
parent_category = "ExampleModRootCategory" # This puts the category into the root category
```

## Crafting Recipe
This is a recipe in the example category, that is also available inside the lifepod fabricator. It crafts 12 titanium from 2 metal salvage and 2 copper. It is unlocked once you have picked up both metal salvage and copper.
<br>[➔ _Learn More_](../data/recipes.md)
```toml
[[recipe]]
id = "ExampleModRecipe"
name = "Example Titanium Recipe"
description = "Using a bit of copper, metal salvage can be used much more efficiently to produce 1.5x the amount of titanium."

icon = "ITEM Titanium" # This statement will use the icon of titanium for the category
category = "ExampleModCategory" # This puts the category in the previously declared category

crafting_time = 5.0 # The crafting time has to have a floating point and is in seconds
available_in_lifepod = true
ordering_index = -999 # This would in most categories push the item to the front

[[recipe.ingredients]]
MetalSalvage = 2
Copper = 2

[[recipe.outputs]] # You should generally not have multiple item types in the output, even though it is possible
Titanium = 12

[[recipe.unlocking_rule]]
set_id = "PickupRuleSet" # Rules with the same set id will be combined into one large rule
pickup_items = [
    "MetalSalvage",
    "Copper"
]
```
