# contextmenu

Display a beautiful material context menu using pure Flutter.

It works both on touch devices and on desktop devices.

## Features

* modern, emphasizing animation according to material design guidelines
* handles screen edges and oversize

## Getting Started

You can easily display a context menu using the following code:
```dart
Widget build() {
  return ContextMenuArea(
    items: [
      ListTile(
        title: Text('Option 1'),
        onTap: () {
          Navigator.of(context).pop();
          ScaffoldMessenger.of(context)
              .showSnackBar(SnackBar(content: Text('Whatever')));
        },
      )
    ],
    child: Card(
      color: Theme
          .of(context)
          .primaryColor,
      child: Center(
        child: Text('Press somewhere for context menu.'),
      ),
    ),
  );
}
```

A more complicated way manually triggering a context menu using `showContextMenu()` is:
```dart
Widget build() {
  return GestureDetector(
    onSecondaryTapDown: (details) => showContextMenu(
        details.globalPosition, context, items, verticalPadding, width),
    child: Text('Tap!'));
}
```

## Setup web

For the web, edit your `index.html` and add the following in the `<body>` tag:
```html
<body oncontextmenu="return false;">
```

## License

This project is EUPL licensed. For further details, consult [LICENSE](LICENSE);