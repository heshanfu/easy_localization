# Changelog

## [1.4.1]

- optimized and clean code
- fixed many issues
- added extension for Strings

  ``` dart
  // after 1.4.1
  Text('title'.tr()),
  Text('switch'.tr( gender: _gender ? "female" : "male")),
  Text('counter'.plural(counter)),
  ```

## [1.4.0]

- refactor code changed call ~~`AppLocalizations.of(context).tr()`~~ ~~`AppLocalizations.of(context).plural()`~~ to `tr()` and `plural()`

  ``` dart
  // after 1.4.0
  Text(
    tr('switch', gender: _gender ? "female" : "male"),
  ),
  ```

  ``` dart
  // before 1.4.0
  Text(
    AppLocalizations.of(context).tr('switch', gender: _gender ? "female" : "male"),
  ),
  ```

- added Flutter extension for Text widget

  ``` dart
  // after 1.4.0
  Text('switch').tr( gender: _gender ? "female" : "male"),
  Text('counter').plural(counter),
  ```

## [1.3.5]

- merge  `gender()`  and `tr()`  .

  ``` json
  {
    "switch":{
      "male": "Hi man ;)",
      "female": "Hello girl :)"
    }
  }
  ```

  ``` dart
  new Text(
    AppLocalizations.of(context).tr('switch', gender: _gender ? "female" : "male"),
  ),
  ```

- use parameters `args` for gender.
  
  ``` json
  {
    "switch":{
      "male": "Hi man ;) {}",
      "female": "Hello girl :) {}"
    }
  }
  ```

  ``` dart
  new Text(
    AppLocalizations.of(context).tr('switch', args:["Naama"] gender: _gender ? "female" : "male"),
  ),

## [1.3.4]

- adeed Gender [female,male]  `gender()`  .

  ``` json
  {
    "switch":{
      "male": "Hi man ;)",
      "female": "Hello girl :)"
    }
  }
  ```

  ``` dart
  new Text(
    AppLocalizations.of(context).gender('switch', _gender ? "female" : "male"),
  ),
  `

## [1.3.3+1]

- updated  `plural()` thanks [shushper](https://github.com/shushper) .

  ``` json
  {
    "text": {
      "day": {
        "zero":"{} дней",
        "one": "{} день",
        "two": "{} дня",
        "few": "{} дня",
        "many": "{} дней",
        "other": "{} дней"
      }
    }
  }
  ```

## [1.3.3]

- removed  `data.savedLocale` .
- optimized and clean code
- fixed many issues

## [1.3.2]

- `plural()` added property resolver for nested key translations

  ``` json
  {
  "text": {
    "day": {
      "zero": "day",
      "one": "day",
      "other": "days"
      }
    }
  }

  ```

  ``` dart
  new Text(
    AppLocalizations.of(context).plural("text.day", 2),
  ),
  ```

- fixed many issues

## [1.3.1]

- add useOnlyLangCode flag

## [1.3.0]

- Load translations from remote or backend
- fixed many issues

## [1.2.1]

- supported shared_preferences
- Save selected localization

## [1.2.0]

- Added property resolver for nested key translations
- return translate key if the element or path not exist

``` json
{
  "title": "Hello",
  "msg": "Hello {} in the {} world ",
  "clickMe": "Click me",
  "profile": {
    "reset_password": {
      "title": "Reset Password",
      "username": "Username",
      "password": "password"
    }
  },
  "clicked": {
    "zero": "You clicked {} times!",
    "one": "You clicked {} time!",
    "other": "You clicked {} times!"
  }
}

new Text(
  AppLocalizations.of(context).tr('profile.reset_password.title'),
 ),
```

## [1.0.4]

- Added Support country codes

## [1.0.3]

- Updated `tr()` function added Multi Argument

## [1.0.2]

- Added string pluralisation .
- Added Argument to `tr()` function.
