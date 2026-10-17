# Melody plugins

Plugins for [Melody](https://github.com/carnager/melody-next): programs of
their own that add entries to Melody's context menus, as its
[plugin guide](https://github.com/carnager/melody-next/blob/main/docs/plugins.md)
describes. Each folder here is one plugin.

## Installing one

Put its folder in Melody's plugin folder, then tick it under
**Settings → Plugins**:

```sh
git clone https://github.com/carnager/melody-plugins ~/Code/melody-plugins
ln -s ~/Code/melody-plugins/dropwatch ~/.local/share/melody/plugins/dropwatch
```

On macOS the plugin folder is `~/Library/Application Support/melody/plugins/`.

## dropwatch

For [dropwatch](https://github.com/carnager/dropwatch), which watches artists
for new releases.

- **Missing albums** (tracks or albums chosen): the albums dropwatch knows of
  that are not in the library, for each artist chosen, in a list -- year and
  type beneath each, a double click opening its MusicBrainz page.
- **Open in dropwatch**: the artist's page in dropwatch, in the browser.

It needs dropwatch's address and an API token (dropwatch: settings ->
Account). Both are read from the environment, else from
`~/.config/dropwatch/client.env`:

```sh
DROPWATCH_URL=http://localhost:8080
DROPWATCH_TOKEN=<token>
```

What it sends: the chosen artists' names, to your dropwatch only.
