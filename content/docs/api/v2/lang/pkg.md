---
tags: [api]
title: lang (package)
slug: pkg

aliases:
- /api/lang/pkg
- /api/lang/pkg.html
- /api/v2.0/lang/pkg
- /api/v2.0/lang/pkg.html
- /api/v2.1/lang/pkg
- /api/v2.1/lang/pkg.html
- /api/v2.2/lang/pkg
- /api/v2.2/lang/pkg.html
- /api/v2.3/lang/pkg
- /api/v2.3/lang/pkg.html
- /api/v2.4/lang/pkg
- /api/v2.4/lang/pkg.html
- /api/v2.5/lang/pkg
- /api/v2.5/lang/pkg.html
- /api/v2.6/lang/pkg
- /api/v2.6/lang/pkg.html
- /api/v2.7/lang/pkg
- /api/v2.7/lang/pkg.html
- /api/lang
- /api/lang.html
- /api/v2.0/lang
- /api/v2.0/lang.html
- /api/v2.1/lang
- /api/v2.1/lang.html
- /api/v2.2/lang
- /api/v2.2/lang.html
- /api/v2.3/lang
- /api/v2.3/lang.html
- /api/v2.4/lang
- /api/v2.4/lang.html
- /api/v2.5/lang
- /api/v2.5/lang.html
- /api/v2.6/lang
- /api/v2.6/lang.html
- /api/v2.7/lang
- /api/v2.7/lang.html

package: fyne.io/fyne/v2/lang
---


---
```go
import "fyne.io/fyne/v2/lang"
```

Package lang introduces a translation and localisation API for Fyne applications.

Translation bundles are JSON files in the format used by github.com/nicksnyder/go-i18n. The simplest form maps each key to its translation directly:

```go
    {
        "Open":   "Ouvrir",
        "Cancel": "Annuler"
    }
```

For plurals or richer messages a value can be an object that uses the reserved keys "id", "description", "hash", "leftdelim", "rightdelim", "zero", "one", "two", "few", "many", "other" and "translation" (matched case-insensitively).

Those reserved words cannot appear as top-level keys in a translation file when other top-level keys are also present — the loader will reject the file with an error such as:

```go
    reserved keys [Description] mixed with unreserved keys [Name Type]
```

If you need to translate one of those words on its own, either pass a more contextual fallback to Localize (lang.L) — for example "Item description" instead of just "Description" — so the derived key avoids the reserved word, or use LocalizeKey (lang.X) with an explicit key, for example lang.X("label.description", "Description").

Since 2.5

## Usage

```go
var (
	// L is a shortcut to localize a string, similar to the gettext "_" function.
	// More info available on the `Localize` function.
	L = Localize

	// N is a shortcut to localize a string with plural forms, similar to the ngettext function.
	// More info available on the `LocalizePlural` function.
	N = LocalizePlural

	// X is a shortcut to get the localization of a string with specified key, similar to pgettext.
	// More info available on the `LocalizeKey` function.
	X = LocalizeKey

	// XN is a shortcut to get the localization plural form of a string with specified key, similar to npgettext.
	// More info available on the `LocalizePluralKey` function.
	XN = LocalizePluralKey
)
```

#### func  AddTranslations

```go
func AddTranslations(r fyne.Resource) error
```
AddTranslations allows an app to load a bundle of translations. The language that this relates to will be inferred from the resource name, for example "fr.json". The data should be in json format following the structure described in the package documentation.

#### func  AddTranslationsFS

```go
func AddTranslationsFS(fs embed.FS, dir string) (retErr error)
```
AddTranslationsFS supports adding all translations in one calling using an `embed.FS` setup. The `dir` parameter specifies the name or path of the directory containing translation files inside this embedded filesystem. Each file should be a json file with the name following pattern [prefix.]lang.json. See the package documentation for the expected file structure.

#### func  AddTranslationsForLocale

```go
func AddTranslationsForLocale(data []byte, l fyne.Locale) error
```
AddTranslationsForLocale allows an app to load a bundle of translations for a specified locale. The data should be in json format.

#### func  Localize

```go
func Localize(in string, data ...any) string
```
Localize asks the translation engine to translate a string, this behaves like the gettext "_" function. The string can be templated and the template data can be passed as a struct with exported fields, or as a map of string keys to any suitable value.

#### func  LocalizeKey

```go
func LocalizeKey(key, fallback string, data ...any) string
```
LocalizeKey asks the translation engine for the translation with specific ID. If it cannot be found then the fallback will be used. The string can be templated and the template data can be passed as a struct with exported fields, or as a map of string keys to any suitable value.

#### func  LocalizePlural

```go
func LocalizePlural(in string, count int, data ...any) string
```
LocalizePlural asks the translation engine to translate a string from one of a number of plural forms. This behaves like the ngettext function, with the `count` parameter determining the plurality looked up. The string can be templated and the template data can be passed as a struct with exported fields, or as a map of string keys to any suitable value.

#### func  LocalizePluralKey

```go
func LocalizePluralKey(key, fallback string, count int, data ...any) string
```
LocalizePluralKey asks the translation engine for the translation with specific ID in plural form. This behaves like the npgettext function, with the `count` parameter determining the plurality looked up. If it cannot be found then the fallback will be used. The string can be templated and the template data can be passed as a struct with exported fields, or as a map of string keys to any suitable value.

#### func  SystemLocale

```go
func SystemLocale() fyne.Locale
```
SystemLocale returns the primary locale on the current system. This may refer to a language that Fyne does not have translations for.

#### types
