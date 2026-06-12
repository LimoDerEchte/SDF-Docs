# Notations

## Item Types
Item types are named `DA_<ItemId>_ItemType` in SN2. When writing item types in SDF, you only use the item id in this template. It will automatically be expanded to the correct format by SDF.

## Scan Data
Scan data is named `DA_<ScanId>_ScanData` in SN2. When writing scan data in SDF, you only use the scan data id in this template. It will automatically be expanded to the correct format by SDF.

## Crafting Recipes
Crafting recipes do not have consistent naming in SN2. Because of this, template expansion for recipes is best explained using this table:

| Recipe Id                                | Notation                              |
|------------------------------------------|---------------------------------------|
| `DA_<SomeRecipe>Recipe`                  | `SomeRecipe`                          |
| `DA_<SomeRecipe>_Recipe`                 | `SomeRecipe`                          |
| `DA_<SomeRecipe>_Recipe<AdditionalData>` | `<SomeRecipe>_Recipe<AdditionalData>` |

When creating new recipes, SDF will always use the first notation.

## Crafting Recipe Categories
Crafting recipe categories are named `DA_<CategoryId>` in SN2. When writing crafting recipe categories in SDF, you only use the category id in this template. It will automatically be expanded to the correct format by SDF.
