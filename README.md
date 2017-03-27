# Droids On Roids: Android Code Style

---

## Config

### Android Studio

Every DOR Android team member should use this code formatting style in Android Studio:

[dor-android-studio.xml](https://github.com/DroidsOnRoids/android-style-guide/blob/master/dor-android-studio-code-style.xml)

This ensures formatting consistency across projects. It also makes code review more pleasant, as it reduces time spent on checking things like missing spaces, wrong indents, etc.

### Project

// TODO:

// Java: checkstyle, findbugs, pmd, sonarqube

// Kotlin: ktlint, detekt

### Continuous Integration

// SonarQube?

---

## Code style

Not all platform and language features will be covered in this repository. Instead, please refer to some good existing ones:

* [Google Java style guide](https://google.github.io/styleguide/javaguide.html)

	Solid general Java style to follow.

* [Ribot Android guidelines](https://github.com/ribot/android-guidelines/blob/master/project_and_code_guidelines.md)

	Good Java and Android-specific practices - apart from *Hungarian Notation*.

* [Buffer Android guidelines](https://github.com/bufferapp/android-guidelines/blob/master/project_style_guidelines.md)

	Similar to Ribot's.

* [A successful XML naming convention](http://jeroenmols.com/blog/2016/03/07/resourcenaming/)

	Good convention for naming Android resource files.

The most important rule is to be consistent within a project.


Only uncertain or controversial topic will be listed here.

---

## Specific topics

### Hungarian notation
Hungarian notation (private/static fields starting with m/s) is generally not recommended. Here's a good write-up on *why not*:

[Just Say mNo to Hungarian Notation (Jake Wharton)](http://jakewharton.com/just-say-no-to-hungarian-notation/)

If you wish to easily remove it from an existing project, see this article about the *Structural Search and Replace* feature of Android Studio:

[Android Studio Like a Boss (Realm.io)](https://realm.io/news/360andev-philippe-breault-android-studio-ide-like-boss-structural-search-refactoring-java/)

### RxJava/Stream chains

Those can get pretty ugly sometimes.

If possible, avoid deep nesting in RxJava/Stream chains. Instead, try to refactor operator arguments into separate methods. A good rule of thumb for clean and readable chains: `one line = one operator`.

### Kotlin

#### Code style

Please refer to Kotlin's website:
[Kotlin Coding Conventions](https://kotlinlang.org/docs/reference/coding-conventions.html)

#### XML

[Kotlin Android Extensions](https://kotlinlang.org/docs/tutorials/android-plugin.html) automatically bind XML-defined views. This allows us to call them through *synthetic properties* without manually using `findViewById()` or *Butterknife*.

Considering that, use *lowerCamelCase* when naming views in XML files (in contrast to *snake_case* in Java projects).

#### Tests

When naming tests, use backticked method names for better readability:

``` `should return negative one when argument is null`() ```
