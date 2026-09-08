# JellySin

A little temptation for your media server.

Independent plugins for **Jellyfin 12**, with shared release tooling and one
catalog. Each plugin owns its code and release cycle.

- [Last.fm](https://github.com/jellysin/jellyfin-plugin-lastfm): music listening,
  favourites, metadata and discovery integration.
- [Plugin tooling](https://github.com/jellysin/plugin-tooling): reproducible packages,
  verified releases and catalog updates.
- [Catalog](https://github.com/jellysin/catalog): one repository URL for JellySin plugins.

Add the catalog in Jellyfin's plugin repository settings:

```text
https://raw.githubusercontent.com/jellysin/catalog/main/manifest.json
```

Plugins appear after their first verified release. Development happens in public;
new source is licensed under EUPL-1.2.
