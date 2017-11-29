# Purpose of this project

The only purpose of this project is to create a sample application which uses the flutter_charts library published on https://pub.dartlang.org/packages/flutter_charts.

There are two potential take aways from this project:

1) This application serves as an overall structure sample for an application that uses a flutter chart.
2) This application's `pubspec.yaml` can be used as a start for an application that uses a flutter chart, loaded as a library package from pub.

## Notes on getting Started

For help getting started with Flutter, view our online
[documentation](http://flutter.io/).

The flutter_charts library on pub is at https://pub.dartlang.org/packages/flutter_charts.

## Possible errors running a Flutter app

The errors described here are generally not related to Flutter Charts, 
they are arrors that can happen for dependency or other reasons. I am 
listing them here to provide a more complete help.

### Running `pub get` results in the error ` Package flutter_charts_sample_app depends on flutter from unknown source "sdk"`

If you get this error running `pub get`:
 
 Resolving dependencies... 
    Package flutter_charts_sample_app depends on flutter from unknown source "sdk".

Reason: Most likely there are incorrect dependencies either in `flutter_charts_sample_app`, or in a library package 
loaded from pub. In one case, I published `flutter_charts` with a specified version of flutter (something like flutter: >=0.0.yy <0.xx.0). 
Apparently one should remove any flutter version before ` flutter packages pub publish` and just use in the published package:

```
dependencies:
  flutter:
    sdk:  flutter
  decimal: ">=0.1.4 <0.2.0"

dev_dependencies:
  test:
  flutter_test:
    sdk:  flutter
```