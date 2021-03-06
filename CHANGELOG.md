# Changelog

## Unreleased

## Releases

### Sketch 69

- [New] Color Variables API.

### Sketch 67

- [Fixed] Return `system` font family name correctly on macOS 10.15

### Sketch 65

- [New] Add `resizeToOriginalSize` method on `Image`.
- [New] Add `size` property on `ImageData`.
- [New] Provide detail of the shared style when syncWithSharedStyle locates a shared style linked to an external library.

### Sketch 63

- [New] Updated `LibraryType` enum.

### Sketch 61

- [New] Variable font API.
- [New] Support for smart layout.
- [Improved] Update to @skpm/process@0.1.4.

### Sketch 59

- [Improved] When setting the `trimmed` option to `false` during an export, it will not trim the image even if there is no background color.
- [New] `onDocumentChanged` handler.

### Sketch 58.1

- [Fixed] `ShapePath.fromSVGPath` no longer throws an error.

### Sketch 57

- [New] Expose the `PointType` enum on `ShapePath`.
- [Fixed] `document.centerOnLayer` not centering on nested layers.

### Sketch 56

- [Fixed] Changing the `pointType` of a CurvePoint wouldn't always restore the control points.
- [Fixed] Do not default to `ShapeType.Rectangle` if some points are specified when create a new ShapePath.
- [Improved] Added multiline functionality to string inputs on `UI.getInputFromUser`.
- [New] Expose substring in `Text.fragment`.
- [New] Add a `find` method to make it easy to look for specific layers.
- [Fixed] Fix setting layers of a group when the layers already had a parent.
- [Fixed] `symbolMaster.getParentSymbolMaster` used to throw an error. It will now return `undefined`.
- [New] Added a `colorSpace` property and a `changeColorSpace` method to `Document`.

### Sketch 55

- [New] Add `isSelected` method on a CurvePoint.
- [Improved] Improve consistency by deprecating `Fill.fill` in favor of `Fill.fileType` (to match `Border.fileType` and other types).
- [Fixed] `getSelectedDocument()` could throw an error when no document was opened. Now it will return `undefined`.

### Sketch 54

- [New] Add `colors` and `gradients` properties on Document.
- [New] `export` now returns a Buffer if `options.output` is `false` and `options.formats` is an image format.
- [Improved] Shared styles are now document properties and can be mutated.
- [Improved] `console.clear` will now clear the DevTools console.
- [Improved] Be more aggressive in finding the selected document.
- [New] Add `pattern` properties on Fill.
- [Fixed] Setting `flow` as `undefined` on a Layer.
- [Improved] `selectedPage` and `selectedLayers` can now be set on the Document.
- [New] Add some methods to deal with the Symbols Page.
- [Improved] `layer.duplicate` now works on a layer with no parent.
- [Fixed] `symbolInstance.master` now works on an immutable instance.
- [New] Add `aspectRatio` property to Gradient.
- [New] Add `selected` property on an Override.
- [New] Add `getFrame` method on an Override.
- [New] add `sketch.globalAssets` property.
- [Improved] `layer.index` can now be set.
- [Fixed] `new Text({ style: {} })` now works as expected.

### Sketch 53.1

- [Fixed] Setting mutable colors where it should.

### Sketch 53

- [Improved] Obj-C exceptions will be thrown as JS Errors which will reference the exception in their `nativeException` property.
- [Improved] `setTimeout` and all the other timeout, interval, immediate methods are now available directly, no need to polyfill them.
- [New] new method on the path module `require('path').resourcePath(resourceName)` which returns the path to a resource in the plugin bundle or `undefined` if it doesn't exist.
- [Improved] The document from a library will now have a proper path (either local path or the appcast URL).
- [New] Add support for Slices.
- [New] Add `exportFormats` property on Layer.
- [Improved] No need to specify the type when there is no choice (like Document.pages can only contain Pages, Layer.exportFormats can only contain ExportFormats, etc.).
- [New] Add UI.getInputFromUser method and deprecate the other input methods.
- [New] Add some `getParent*` methods on Layer.
- [New] Add `ShapeType` to create different shapes.
- [New] Add support for text styles.
- [New] Add some methods to store a session variable.
- [Improved] Allow using setting methods even from the Run Script panel.
- [New] Add method to get the theme of Sketch.
- [New] `export` can now export to the JSON file format.
- [New] Add `background` property on Artboard.
- [New] Add `transform` property on Layer.
- [New] Add `editable` property on Override.
- [New] Add `overrides` property on Symbol Master to be able to change their `editable` property.
- [Improved] Add an options parameter when detaching a Symbol Instance.

### Sketch 52.1

- [New] Add basic support for Shape path.

### Sketch 52

- [Improved] Make sure Document.save will not overwrite a folder by mistake.
- [Fixed] Using 0 as a shadow's value shouldn't fall back to the default.
- [Fixed] Logging an NSArray would print an array of `undefined` instead of the proper items.
- [Fixed] Adding a remote library for the first time will now return the library instead of an error.
- [Fixed] Adding a remote library will also download it right away.
- [Fixed] Printing a missing Library.
- [New] Data Plugin!.
- [New] Add support for SharedStyle.
- [New] Add support for Immutable native model objects.
- [New] Add `affectedLayer` for Override.
- [Improved] Allow storing a setting on an Override or DataOverride.
- [Improved] Settings will now be serialized even if they are of native types.

### Sketch 51

- [New] Add `path` property to Document.
- [New] Add `lastModifiedAt` property to Library.
- [New] Disable/Enable a Library by setting its `enabled` property.
- [New] Add `buffer`, `os`, `path` and `timers` core modules.
- [New] Add method to add a remote library from an RSS feed.
- [Improved] console.log a wrapped object should be a lot faster on complex files.
- [Fixed] Logging a MOStruct (such as NSRange for example) would error.
- [Fixed] Getting the importable objects from a Library would sometime returns the ones from another library that shares the same id.
- [Fixed] Setting an image override on a symbol instance.
- [Fixed] Saving a document without specifying a path would fail.
- [Fixed] Opening a document without a path would fail.
- [Fixed] Setting the `to` of a gradient would actually change the `from`.

### Sketch 50.1

- [Improved] Add `Rectangle.changeBasis` method and deprecate the specific implementations from Layer and Group.
- [Fixed] Add missing wrapper for some libraries.

### Sketch 50

- [Fixed] Creating a Rectangle with an Object having an `x` value of `0` now works as expected.
- [New] Add `locked` and `hidden` property on Layer.
- [New] Add `console` core module (accessed with `require('console')`.
- [New] Add `util` core module (accessed with `require('util')`.
- [New] Add `events` core module (accessed with `require('events')`.
- [New] Add `console` global.
- [Fixed] Mutating a frame's Rectangle will change the frame.
- [New] Add support for Libraries.
- [New] Add `save`, `open`, and `close` method on Document.
- [Improved] Add support for style on all the layers.
- [Improved] Add support for Shadows, Inner Shadows, opacity, blur, border options, blending mode, and gradients in Style.

### Sketch 49.1

- [New] Add `HotSpot` component.
- [New] Add convinient array methods to Selection.
- [Improved] A Shape is now created with a default rectangle path.
- [Fixed] Add a new Page with `new sketch.Page({ parent: document })`.
- [Fixed] Add `SymbolInstance.setOverrideValue()` method.
- [Fixed] `Artboard.adjustToFit()` now works as expected.
- [Fixed] Setting the stystem font size of a Text now works as expected.
- [Fixed] Exporting a Page now works as expected.
- [Fixed] `Document.getLayersNamed()` now works as expected.

- [New] First release of the new AP
