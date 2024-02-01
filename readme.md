## [Set up app links for Android](https://docs.flutter.dev/cookbook/navigation/set-up-app-links)

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

---

### apple-app-site-association

1. webcredentials": "webcredentials"는 Associated Domains 설정에 추가되는 키로, 앱과 관련된 웹 자격 증명을 지정하는 데 사용됩니다. 이를 통해 사용자가 웹 사이트에 로그인할 때 앱과의 싱크를 맞출 수 있습니다. "webcredentials" 키에는 앱의 도메인 이름을 지정해야 합니다.

2. "appclips": "appclips"는 iOS 14부터 도입된 기능으로, 앱의 일부 기능을 즉시 사용할 수 있는 작은 앱 클립을 제공합니다. "appclips"를 설정하면 사용자가 특정 액션을 수행할 때 앱의 일부 기능을 빠르게 실행할 수 있습니다.
