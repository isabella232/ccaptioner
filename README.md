## CCaptioner

A very simple extension which purpose is to assign a text track to a [HTML5
`video` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)
in a web page.

![ccaptioner's popup panel](https://user-images.githubusercontent.com/585534/73291383-10413a00-41ce-11ea-9cbd-25ab7be7802d.png)

Many HTML5 video players do not offer the ability to import text track for
captions/subtitles purpose. The purpose of this extension is to remediate
this problem.

When you want to assign a text track to a video element in a web page:

- Open the popup menu and click __"Assign text track to..."__
- Move the mouse over the target video element
    - Click the video element if needed
- A file picker will appear
- Pick the `.srt` or `.vtt` file to use as text track

The video should now render the captions/subtitles of the file you
selected.

The content scripts of CCaptioner are injected **if and only if** you click on
its toolbar icon while on a specific web site, and only for that web site.
Once the text track is embedded, the content script terminates and should be
garbage-collected by your browser's JavaScript engine.

Once a text track has been assigned to a video element on a given page, you
can time-shift the text track through CCaptioner's popup panel -- this is
useful when the text track is not well synchronized with the video content.

### Permissions

#### `activeTab`

This permission means that the extension will be able to interact
with a web page **only** when you click its icon in the toolbar; so
CCaptioner's content script is injected **only** when you demand it by clicking
CCaptioner's toolbar icon.

#### `<all_urls>`

This permission is necessary to ensure CCaptioner's content script can also be
injected in embedded `iframe` elements in a page -- it is not uncommon for
video players to be inside an `iframe` which origin is different from the
origin of the root document.

### Credits

The CCaptioner's icon is from <https://en.wikipedia.org/wiki/File:Closed_captioning_symbol.svg>.
