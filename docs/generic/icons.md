# Icon Notation
## Basic Structure
Icons in the SDF always follow the scheme that is described below. There are ongoing efforts to make a built-in icon creator, that can combine icons at runtime, but it is not entirely sure if this will ever actually be added to the SDF.

The item notation always consists off a specific type of icon and specific arguments corresponding to that type. The types and their specific arguments are described in the table and subsections below.

``TYPE <Args>``

## Icon Types
This table contains all icon types. Additional information is available below.

| Type    | Arguments                            | Description                                                        |
|---------|--------------------------------------|--------------------------------------------------------------------|
| DEFAULT | None                                 | The Alterra Cicada icon, usually used for placeholders in the game |
| ITEM    | [Item Type](../generic/notations.md) | Uses the icon of a specific item type                              |
| FILE    | [Subtype, Path](#file-type)          | Uses an icon from a user specified file                            |

### File Type
``FILE <Subtype> <Path>``

#### Subtype
To show better where these are resolved to, we will assume an example mod at `/ue4ss/Mods/ExampleMod/`

| Subtype | Location                      |
|---------|-------------------------------|
| UE4SS   | `/ue4ss/`                     |
| MOD     | `/ue4ss/Mods/ExampleMod/`     | 
| SDF     | `/ue4ss/Mods/ExampleMod/SDF/` |

#### Path
This is the relative path from your specified subtype location to the image file. It has to include the file extension.