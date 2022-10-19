# Testing in Jetpack Compose with BrowserStack App-Automate

## Build the App

Run the command:
`./gradlew app:assembleDebug`

## Build the Test Suite

Run the command:
`./gradlew app:assembleAndroidTest`

## Upload the App to BrowserStack

```shell
 curl -u "BROWSERSTACK_USERNAME:BROWSERSTACK_ACCESSKEY" \
-X POST "https://api-cloud.browserstack.com/app-automate/espresso/v2/app" \
-F "file=@/path/to/app/file/Application-debug.apk"
```

## Upload the Test Suite to BrowserStack

```shell
curl -u "BROWSERSTACK_USERNAME:BROWSERSTACK_ACCESSKEY" \
-X POST "https://api-cloud.browserstack.com/app-automate/espresso/v2/test-suite" \
-F "file=@/path/to/app/file/Application-debug-test.apk"
```

## Execute Tests on BrowserStack

```shell
curl -u "BROWSERSTACK_USERNAME:BROWSERSTACK_ACCESSKEY" \
-X POST "https://api-cloud.browserstack.com/app-automate/espresso/v2/build" \
-d '{"app": "bs://<APP_URL>", "testSuite": "bs://<TEST_SUITE_URL>", "devices": ["Samsung Galaxy S21-11.0"], "class": ["com.example.compose.rally.OverviewScreenTest", "com.example.compose.rally.TopAppBarTest"]}' \
-H "Content-Type: application/json"
```

## Refrences

- [BrowserStack App-Automate Dashboard](https://app-automate.browserstack.com/dashboard/v2/)
- [Using Espresso with BrowserStack](https://www.browserstack.com/app-automate/espresso/get-started)
- [Filter Test cases on Espresso](https://www.browserstack.com/docs/app-automate/espresso/select-test-cases)

---

## Note

This folder contains the source code for the
[Testing in Jetpack Compose Codelab ](https://developer.android.com/codelabs/jetpack-compose-testing)
codelab.

## License

```
Copyright 2021 The Android Open Source Project

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
