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

\* marks required attributes

The attribute `crafted_by` can be one of the following:</br>
`Fabricator, ModificationStation, Processor, BuilderTool, VehicleFabricator`

## The parent category
The parent category is the defining factor for where a category is located. If you want a new category in the main menu of any fabricator, you only have to set the `crafted_by` attribute to your desired fabricator. If you want to have your category inside another one, like the different subcategories in the fabricator, you will have to find out the [recipe category notation](../generic/notations.md#crafting-recipe-categories) for the specific parent category and use it as the `parent_category` attribute.

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
