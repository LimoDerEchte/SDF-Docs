# Crafting Recipe Categories
## Basic Crafting Recipe Categories
You can create recipe categories using a structure like this in any TOML file of the project:

```toml
[[category]]
id = "CategoryId"
...
```

### All entries under `[[category]]`

| Key             | Type   | Value                                                                                                           |
|-----------------|--------|-----------------------------------------------------------------------------------------------------------------|
| id*             | string | Unique identifier ([recipe category notation](../generic/notations.md#crafting-recipe-categories))              |
| name*           | string | The name that will be used throughout the game for this recipe category                                         |
| description     | string | The categories description - currently unused ingame                                                            |
| crafted_by*     | string | This defines what kind of recipe lives in this category                                                         |
| parent_category | string | The categories parent category ([recipe category notation](../generic/notations.md#crafting-recipe-categories)) |
| icon            | string | The categories icon ([icon notation](../generic/icons.md))                                                      |
| ordering_index  | int    | The ordering index is relevant for the order recipe categories are displayed in                                 |
| show_when_empty | bool   | Marks if the category should be visible, even when it has no recipes (WIP)                                      |

\* marks required attributes

The attribute `crafted_by` can be one of the following:</br>
`Fabricator, ModificationStation, Processor, BuilderTool, VehicleFabricator`

## Modifying Crafting Recipe Categories
You can modify crafting recipe categories like this:
```toml
[[category_modify]]
id = "CategoryIdToModify"
...
```
The recipe id follows the [recipe category notation](../generic/notations.md#crafting-recipe-categories).

You can use fields from the standard `[[category]]` notation, to modify aspects of the recipe category.

## Deleting Crafting Recipe Categories
You can delete crafting recipe categories like this:
```toml
[[category_delete]]
id = "CategoryIdToDelete"
```
The recipe id follows the [recipe category notation](../generic/notations.md#crafting-recipe-categories).
