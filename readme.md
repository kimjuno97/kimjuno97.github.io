# [Set up app links for Android](https://docs.flutter.dev/cookbook/navigation/set-up-app-links)
[Android 앱 링크 인증하기](https://developer.android.com/training/app-links/verify-android-applinks?hl=ko)

[flutter keystore](https://docs.flutter.dev/deployment/android)

- flutter project 키 저장소 파일 생성

```
keytool -genkeypair -v -keystore my-release-key.keystore -keyalg RSA -keysize 2048 -validity 10000 -alias my-key-alias
```

- key 보기

```
keytool -list -v -keystore my-release-key.keystore
```

- Certificate fingerprints의 'SHA256' 찾기
