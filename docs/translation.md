# Translation

Test output and the way tests are written can be localized.

CodeceptJS provides built in translations to:

* `ru-RU`
* `pt-BR`

They can be enabled in config file like:

```json
  "translation": "ru-RU"
```

By enabling this feature and running with `--steps` option steps will be translated:

```
 signin
 • Я на странице "https://github.com"
 • Я кликаю "Sign in"
 • Я вижу "Sign in to GitHub"
 • Я заполнаю поле "Username or email address", "something@totest.com"
 • Я заполнаю поле "Password", "123456"
 • Я кликаю "Sign in"

```

This also enables localized method names for actor object.

This way tests can be written in native language while it is still JavaScript:

```js
Scenario('пробую написать реферат', (Я) => {
    Я.на_странице('http://yandex.ru/referats');
    Я.вижу("Написать реферат по");
    Я.выбираю_опцию('Психологии');
    Я.кликаю("Написать реферат");
    Я.вижу("Реферат по психологии");
});
```

To get autocompletion for localized method names generate definitions by running

```
codeceptjs def
```