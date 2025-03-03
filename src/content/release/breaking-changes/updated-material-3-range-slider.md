---
title: Updated Material 3 `RangeSlider`
description: >-
  The `RangeSlider` widget has been updated to match the
  Material 3 Design specifications.
---

## Summary

The `RangeSlider` has been updated to match the Material 3 Design specifications.

The `RangeSlider` changes include an updated height,
gaps between the active and inactive tracks, and
stop indicators to show the range of values in the tracks.
Pressing the thumbs adjusts their width, and the tracks adjust their shape.
The new value indicator shape is a rounded rectangle.
New color mappings have also been introduced for some of the `RangeSlider` shapes.

## Context

The Material 3 Design specs for the `RangeSlider` were updated in December 2023.
To opt into the 2024 design spec, set the `RangeSlider.year2023` flag to `false`.
This is done to ensure that existing apps aren't affected by
the updated design specifications.

## Description of change

The `RangeSlider` widget has a `year2023` flag that can be set to `false` to
opt in to the updated design spec.
The default value for the `year2023` flag is `true`,
which means that the `RangeSlider` uses the previous 2023 design specifications.

When [`RangeSlider.year2023`][] is set to `false`,
the slider uses the updated design specifications.

## Migration guide

To opt into the updated design spec for the `RangeSlider`,
set the `year2023` flag to `false`:

```dart highlightLines=2
RangeSlider(
  year2023: false,
  values: _currentRangeValues,
  max: 100,
  onChanged: (RangeValues values) {
    setState(() {
      _currentRangeValues = values;
    });
  },
),
```

To update your entire app to use the updated `RangeSlider` design, set the
`SliderThemeData.year2023` property to `false` in your `MaterialApp`:

```dart highlightLines=2
return MaterialApp(
  theme: ThemeData(sliderTheme: const SliderThemeData(year2023: false)),
    // ...
    RangeSlider(
      values: _currentRangeValues,
      max: 100,
      onChanged: (RangeValues values) {
        setState(() {
          _currentRangeValues = values;
        });
      },
    ),
    // ...
```

## Timeline

Landed in version: TBD<br>
In stable release: TBD

## References

API documentation:

* [`RangeSlider`][]
* [`RangeSlider.year2023`][]

Relevant issues:

* [Update `RangeSlider` for Material 3 redesign][]

Relevant PRs:

* [Update the `RangeSlider` widget to the 2024 Material Design appearance][]

[`RangeSlider`]: {{site.main-api}}/flutter/material/RangeSlider-class.html
[`RangeSlider.year2023`]: {{site.main-api}}/flutter/material/RangeSlider/year2023.html
[Update `RangeSlider` for Material 3 redesign]: {{site.repo.flutter}}/issues/162505
[Update the `RangeSlider` widget to the 2024 Material Design appearance]: {{site.repo.flutter}}/pull/163736
