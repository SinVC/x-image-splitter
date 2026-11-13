# Four Slices for X

[中文说明](README.zh-CN.md)

A Chrome extension that splits a wide image into up to 20 vertical slices and adds them to X posts. Preview the slices in order before adding them, without manually saving image files.

## Features

- Drag in, select, paste, or read a copied image from the clipboard.
- Accept JPG, PNG, and WebP; output JPG or PNG.
- Enter a slice count from 1 to 20. The default is 4. Slices are numbered from left to right.
- Preview the slices and add them to an empty X post attachment area.

The extension's interface is currently in Chinese.

## Install

1. Open `chrome://extensions` in Chrome and turn on **Developer mode**.
2. Click **Load unpacked** and select this project's `extension` folder.
3. Refresh X. The **四片** button appears on the page.

Chrome may ask for clipboard access. The extension reads the clipboard only when you click **读取剪贴板并切图** (Read clipboard and split).

## Use

1. Open the X post composer and expand **四片**.
2. Drop or select an image, paste one into the panel, or right-click an image in your browser, choose **Copy image**, and click **读取剪贴板并切图**.
3. Enter the slice count in **份数** and check the preview. Click **加入当前帖子** (Add to current post).
4. Check the attachments in X before posting.

The attachment area must be empty. X accepts up to four images per post. For more than four slices, open a new empty composer and click **加入当前帖子** for each remaining batch. Clipboard images usually do not include the original filename, so their slices use a timestamped name.

## Development

Install [Bun](https://bun.com/), then run from the project directory:

```sh
bun build.ts
bun test tests/clipboard.test.ts
```

The build updates `extension/` and the loadable files in the project root. After rebuilding, reload the extension in `chrome://extensions` and refresh X.
