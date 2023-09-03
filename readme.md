# [Set up app links for Android](https://docs.flutter.dev/cookbook/navigation/set-up-app-links)

#### [blog post](https://kimjunho97.tistory.com/21)

[Android 앱 링크 인증하기](https://developer.android.com/training/app-links/verify-android-applinks?hl=ko)

[flutter keystore](https://docs.flutter.dev/deployment/android)

- flutter project에 로컬 키 저장소 파일 생성

```
keytool -genkeypair -v -keystore my-release-key.keystore -keyalg RSA -keysize 2048 -validity 10000 -alias my-key-alias
```

- key 보기

```
keytool -list -v -keystore my-release-key.keystore
```

- Certificate fingerprints의 'SHA256' 찾기

- test

```
adb shell 'am start -a android.intent.action.VIEW \
    -c android.intent.category.BROWSABLE \
    -d "http://kimjuno97.github.io/details"' \
    com.example.deeplink_cookbook
```

```
Starting: Intent { act=android.intent.action.VIEW cat=[android.intent.
category.BROWSABLE] dat=http://kimjuno97.github.io/... pkg=com.
example.deeplink_cookbook }
```

---

## [IOS universal-links](https://docs.flutter.dev/cookbook/navigation/set-up-universal-links)

#### [blog post](https://kimjunho97.tistory.com/22)

- test

```
xcrun simctl openurl booted https://kimjuno97.github.io/details
```
