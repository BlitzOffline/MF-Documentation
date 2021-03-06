---
description: Simple GUI that allows you to have multiple pages and navigate between them.
---

# Paginated GUI

![](../../.gitbook/assets/ezgif-6-90e434269b68.gif)

### Creating a Paginated GUI

To create a Paginated GUI all you need to do is:

```java
// Main constructor
PaginatedGui paginatedGui = new PaginatedGui(6, 45, "GUI Title");

// Alternative
PaginatedGui paginatedGui = new PaginatedGui(6, "GUI Title");
```

Just like the normal [GUI](gui.md) the first parameter is the rows the GUI should have. The second parameter is to specify the page size, as in how big the page should be, in the example above it's 45 slots dedicated for the page, if nothing is set the lib will calculate the page size when opening.

### Creating the navigation

To create the navigation items we can simply do:

```java
// Previous item
paginatedGui.setItem(6, 3, ItemBuilder.from(Material.PAPER).setName("Previous").asGuiItem(event -> paginatedGui.previous()));
// Next item
paginatedGui.setItem(6, 7, ItemBuilder.from(Material.PAPER).setName("Next").asGuiItem(event -> paginatedGui.next()));
```

Recommended to add a default click action to cancel the click even when working with pagination, if not, then make sure the navigation item cancels the click before doing `PaginatedGui#next/previous` .

### Populating the page

To add items to the page once again we use the `PaginatedGui#addItem` which takes a `GuiItem`. Items added with `PaginatedGui#setItem` will not be counted towards the page but as static GUI items.

