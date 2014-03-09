> Navigation generator plugin for Assemble

Working spec below

#Here's what I'm thinking how such a plugin might work…

The directory hierarchy of the site would be used to infer the navigation hierarchy. For example, if the site root has a directory named "products" then the main navigation might have a "Products" link with the directory's children listed below as links.

The plugin would parse the pages array from the context data to build a hierarchal navigation object that is then added back into the context.

The site builder can then pass that navigation object to a template/partial to build the menu.

The plugin would have sensible defaults that can be overridden in the task config, front-matter, etc. By default, the plugin might create one navigation called "main" and place all pages into it, sorted by page title. The site builder could override this default by adding a new navigation called "footer", and then update the front-matter of some pages to indicate that the page belongs in "footer" instead of "main". A similar method could be used to specify a custom sort order, use an alternative title in the menu, etc.

The data passed to each page's template would also be altered for each page to indicate the current page and it's parents.