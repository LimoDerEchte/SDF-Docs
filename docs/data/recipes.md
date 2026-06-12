# Crafting Recipes
## Basic Recipes
You can create recipes using a structure like this in any TOML file of the project:

```toml
[[recipe]]
id = "RecipeId"
...

[[recipe.ingredients]]
ItemType = 2
AnotherItemType = 1
...

[[recipe.outputs]]
OutputItemType = 1
...
```

### All entries under `[[recipe]]`

| Key                  | Type   | Value                                                                                                 |
|----------------------|--------|-------------------------------------------------------------------------------------------------------|
| id*                  | string | Unique identifier ([recipe notation](../generic/notations.md#crafting-recipes))                       |
| name*                | string | The name that will be used throughout the game for this recipe                                        |
| description*         | string | The description that will be used throughout the game for this recipe                                 |
| category*            | string | The recipes category ([recipe category notation](../generic/notations.md#crafting-recipe-categories)) |
| icon                 | string | The recipes icon ([icon notation](../generic/icons.md))                                               |
| crafting_time        | float  | The time it takes for this to craft in seconds - default to 2.0                                       |
| available_in_lifepod | bool   | Marks if the recipe should be available in the lifepods fabricator                                    |
| ordering_index       | int    | The ordering index is relevant for the order recipes are displayed                                    |

\* marks required attributes

### Entries under `[[recipe.ingredients]]` and `[[recipe.outputs]]`
These entries consist of a key and a value. The key represents an item type ([item notation](../generic/notations.md#item-types)). The value represents the count of items of that specific type.

## Adding Unlocking Conditions
You can add unlocking conditions to recipes like this:

```toml
[[recipe.unlocking_rule]]
set_id = "SetId"
...
```

The set id is always required and has to be a string. Unlocking rules with the same set id will be combined during parsing.

A recipe is unlocked by fully completing any given set of rules. For a set with the rule sets a and b, this means it unlocks the moment all conditions of either a or b are completed.

### All entries under `[[recipe.unlocking_rule]]`
At least one of these entries has to be present in any given rule.

| Key          | Type         | Value                                                                                                       |
|--------------|--------------|-------------------------------------------------------------------------------------------------------------|
| pickup_items | string array | List of items that need to be picked up at least once ([item notation](../generic/notations.md#item-types)) |
| scan_data    | string array | List of scan data that needs to be fully scanned ([scan data notation](../generic/notations.md#scan-data))  |

## Modifying Crafting Recipes
You can modify crafting recipes like this:
```toml
[[recipe_modify]]
id = "RecipeIdToModify"
...
```
The recipe id follows the [recipe notation](../generic/notations.md#crafting-recipes).

You can use fields from the standard `[[recipe]]` notation, to modify aspects of this item. The following attributes are available in addition to the standard ones:

| Key                         | Type | Value                                                       |
|-----------------------------|------|-------------------------------------------------------------|
| remove_unlocking_conditions | bool | If true, removes all conditions required to unlock the item |

When modifying unlocking conditions, inputs and outputs, please use `[[recipe_modify.<...>]]`. This will also clear the original list of entries.

## Deleting Crafting Recipes
You can delete crafting recipes like this:
```toml
[[recipe_delete]]
id = "RecipeIdToDelete"
```
The recipe id follows the [recipe notation](../generic/notations.md#crafting-recipes).
