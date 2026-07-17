#Revit Tools — pyRevit Extension

Author: **Chulan Adasuriya**  ·  Version: **V.1.0.0**

Tab **FamilyTools** → panel **Families** → two buttons:

## Family Browser  (dark-purple UI)
Lists every loadable family in the current model, split into **Model** and
**Annotation** categories (toggle at the top), previews the selected family,
and places it.
- **Show:** Model / Annotation toggle to scroll each list separately.
- Pick a **Category**, then a **Family** — a preview image of the family is
  shown below.
- **Show Chart** — families & types per category in the output window.
- **Place** — activates the family's first type and starts Revit's native
  placement (switch type in Properties, click points, Esc to finish).

## Element Count
Counts all Model + Annotation element instances in the model, grouped by
category, and shows a bar chart (top 30 categories) plus a full table in the
pyRevit output window.

## Folder structure
```
FamilyTools.extension/
└─ FamilyTools.tab/
   └─ Families.panel/
      ├─ _layout
      ├─ Family Browser.pushbutton/  (script.py, FamilyBrowser.xaml, icon.png)
      └─ Element Count.pushbutton/   (script.py, icon.png)
```

## Install
Requires pyRevit (free).
1. Unzip and place `FamilyTools.extension` somewhere permanent.
2. Revit → **pyRevit** → **Settings** → *Custom Extension Directories* →
   **Add Folder** → choose the folder that **contains** `FamilyTools.extension`.
3. Click **Reload** on the pyRevit tab (or restart Revit).

## Notes
- Requires Revit 2017+ (uses `PostRequestForElementTypePlacement`).
- Annotation families place into the active view, so be in a suitable view
  before placing tags or symbols.
