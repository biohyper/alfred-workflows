Keep a list of audiovisual content to watch and listen to.
 
We often have series of videos and streams that we’d like to watch but not necessarily keep after, but tracking which we’ve already seen (and are thus safe to delete) can be a chore.
 
Select in the Finder the files or directories you wish to add to your list and apply the file action `Add to watchlist`. Every time you do this the new items will be prepended or appended to the list (depending on the `add_item_order` Workflow Environment Variable). Alternatively, call `swl` to add the URL in your clipboard as a stream.

You then have some options you can pick from, all starting with `wl`.

![](https://i.imgur.com/jOKRSwY.png)

`wlp` shows the list of items you can play. A reference to each subtitle section can be found at the end.

![](https://i.imgur.com/anCe2I8.png)

`wls` calls `wlp` under the hood, but lets you first select a sort order based on duration or size.

![](https://i.imgur.com/q8UDKn4.png)

In both cases, ↵ plays the selection. Add ⌘ to play without marking as watched or ⌥ to rescan a directory (useful if you made manual changes to it).

Items starting with `≈` are streams. They show no file size (since they aren’t taking up any space locally) and present the link they were taken from as opposed to a location on disk. To be able to stream video and audio you need either [mpv](http://mpv.io/) or [VLC](http://www.videolan.org/vlc/index.html).

`wlu` marks an item as unwatched. Note that in the case of files it does not recover them from the trash, as there is no reliable way to do so on macOS — that step you need to do yourself. If the item has a URL origin (you’ll see it in the subtitle) add ⌘ to open the URL in your default browser or ⌥ to copy it to the clipboard.

![](https://i.imgur.com/XK0W6Wj.png)

`wle` allows you to reorder, rename, and remove items from the list.

Finally, if you use [DownVid](https://github.com/vitorgalvao/alfred-workflows/tree/master/DownVid) it has an option to add the downloaded video files directly to your watchlist.

#### Subtitle reference:

There are three types of items: `files`, `series`, and `streams`. `stream`s can be further categorised into single item or playlist. Each result has its name as the top title. The subtitle confers more detailed information and follow this template (`~` means it never shows):

```
≈ (4) 𐄁 22m 32s 𐄁 691M 𐄁 /Some/Path
```

+ ≈. Indicates item is a `stream`.
    + `file`: ~
    + `series`: ~
    + `stream`: Always present.
+ (4). Number of elements.
    + `file`: ~
    + `series`: Remaining audiovisual files in directory.
    + `stream`: Single item: ~. Playlist: All elements.
+ 22m 32s. Running time.
    + `file`: Running time of file.
    + `series`: Running time of first audiovisual file in directory.
    + `stream`: Combined running time of all elements.
+ 691M. Size.
    + `file`: Size of file.
    + `series`: Size of first audiovisual file in directory.
    + `stream`: ~
+ /Some/Path. Path.
    + `file`: Path of file.
    + `series`: Path of directory.
    + `stream`: URL.
