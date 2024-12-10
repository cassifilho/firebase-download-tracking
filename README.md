# firebase-download-tracking
Documentação para tracking de downloads com Firebase
# Tracking de Downloads com Firebase

## 📄 Objetivo
Estudo para rastrear downloads no app utilizando o Firebase SDK.

## 📱 Instruções para Android
- Adicionar o Firebase ao projeto.
- Atualizar o Gradle.
- Rastrear eventos com:
  ```kotlin
  FirebaseAnalytics.getInstance(this).logEvent("file_download", Bundle().apply {
      putString("file_name", "example_file.pdf")
      putDouble("progress", 100.0)
  })
## 🍎 Instruções para IOS
- Adicionar o Firebase ao projeto no Xcode.
- Atualizar o Podfile
- Rastrear eventos com:
  Analytics.logEvent("file_download", parameters: [
    "file_name": "example_file.pdf",
    "progress": 100.0
])

