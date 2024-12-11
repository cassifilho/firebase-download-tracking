# firebase-download-tracking  
**Documentação para tracking de downloads com Firebase**


## 📄 Objetivo
Estudo para rastrear downloads no app utilizando o Firebase SDK.

## 📱 Instruções para Android
1. Adicionar o [Firebase ao projeto.](https://firebase.google.com/docs/android/setup?hl=pt)
2. Atualizar o Gradle.
```kotlin
./gradlew wrapper --gradle-version 8.2.1 --distribution-type all
```

3. Rastrear eventos com:
   ```kotlin
   FirebaseAnalytics.getInstance(this).logEvent("file_download", Bundle().apply {
       putString("file_name", "example_file.pdf")
       putDouble("progress", 100.0)
   })
   ```

## 🍎 Instruções para iOS 
1.Adicionar o [Firebase ao projeto no Xcode.](https://firebase.google.com/docs/ios/setup?hl=pt-br)

2. Atualizar o Podfile.

```kotlin
pod install --repo-update
```

3. Rastrear eventos com:
  ```kotlin 
  Analytics.logEvent("file_download", parameters: [ 
    "file_name": "example_file.pdf", 
    "progress": 100.0 
])
```

## 📊 Resultados Obtidos:
1. Android: O evento foi registrado corretamente no Firebase Analytics e exibido nas métricas de eventos no console.
2. iOS: O evento foi rastreado corretamente no Firebase Analytics, e os dados foram enviados com sucesso para o painel de análise.
## 🔧 Funcionalidades Possíveis com o SDK do Firebase:
1. Rastreamento de eventos customizados: Adicionar novos parâmetros ao evento, como tempo de download ou tipo de arquivo.
2. Rastreamento em tempo real: Monitorar o progresso do download em tempo real e enviar atualizações incrementais ao Firebase.
3. Integração com outros produtos Firebase: Integrar com Firebase Crashlytics para capturar falhas durante o download ou com Firebase Remote Config para alterar parâmetros de tracking.
## 🔗 Integração com Google Ads
## 📈 Google Ads Integration
A integração com o Google Ads pode ser feita por meio do Google Analytics para Firebase. O Firebase é usado para rastrear eventos e ações dos usuários no aplicativo, como instalações, compras e interações. Esses eventos são enviados ao Google Ads para otimizar as campanhas e mensurar a eficácia.
Passos principais:

1. Configuração do Google Analytics no Firebase:

- Acesse o Firebase Console.
- Crie um novo projeto ou use um existente.
- Vá para a seção Analytics e habilite o Google Analytics para o seu projeto      Firebase.
- Siga as instruções para adicionar o Firebase SDK ao seu aplicativo Android ou iOS.
- No caso do app React Native, use a biblioteca react-native-firebase.
Configuração do Google Ads:

2. Acesse sua conta do Google Ads.
- Clique em Ferramentas e Configurações (ícone de chave) no canto superior direito.
- Selecione Linked accounts e depois escolha Firebase.
- Siga os passos para vincular sua conta do Firebase à sua conta do Google Ads.
3. Enviar eventos do Firebase para o Google Ads:
- No Firebase, vá para Analytics > Events e registre os eventos que deseja monitorar (como instalação do app, compras ou cliques).
- No Google Ads, você pode configurar ações de conversão com base nos eventos que você rastreou no Firebase. Quando um evento ocorre (por exemplo, uma compra), o Google Ads ajusta automaticamente suas campanhas com base nesses dados.

## 📱 SDK do Firebase para React Native
O SDK do Firebase para React Native permite monitorar e registrar eventos no seu aplicativo, como interações e compras. Esses eventos são configurados no Google Analytics e vinculados diretamente ao Google Ads para otimizar campanhas.
Passos principais:

1. Instalação do SDK do Firebase para React Native:

- Instale a biblioteca @react-native-firebase/app no seu projeto:
```kotlin 
  yarn add @react-native-firebase/app
  ```
 - Para Android:
Siga as instruções em [Firebase Setup - Android](https://firebase.google.com/docs/android/setup?hl=pt-br)
 - Para IOS:
Siga as instruções em [Firebase Setup - iOS](https://firebase.google.com/docs/ios/setup?hl=pt-br) 
2. Configuração do Google Analytics no Firebase:
  - Após instalar o SDK, configure o Analytics:
  ```kotlin
  yarn add @react-native-firebase/analytics
  ```
- No código React Native:
```kotlin 
import analytics from '@react-native-firebase/analytics';
```
3. Registrar eventos customizados:

- Você pode registrar eventos específicos de interações ou ações do usuário. Exemplo para monitorar um download:
 ```kotlin
 await analytics().logEvent('file_download', {
  file_name: 'example_file.pdf',
  progress: 100.0
});
```
4. Vincular eventos ao Google Ads:

- Com os eventos configurados no Firebase Analytics, eles serão automaticamente  enviados para o Google Ads (caso tenha vinculado sua conta do Firebase ao Google Ads, como descrito na seção anterior).

### 🎯 Google Ads Conversion Tracking
O Google Ads Conversion Tracking é utilizado para monitorar o desempenho das campanhas, como cliques em anúncios que resultam em instalações do app ou ações específicas dos usuários, como compras ou registros.

Passos principais:

1. Configuração do Acompanhamento de Conversões no Google Ads:

- Acesse o Google Ads e vá até Ferramentas e Configurações > Acompanhamento de Conversões.
- Clique em + Conversão e escolha App como tipo de conversão.
- Siga as instruções para configurar o acompanhamento de conversões.

2. Vincular Firebase ao Google Ads para Conversões:
- No Firebase Console, vá até Analytics > Ações de conversão e configure eventos específicos que você deseja acompanhar como conversões (por exemplo, instalações ou compras).
- No Google Ads, adicione essas conversões para ajustar suas campanhas com base no comportamento do usuário dentro do app.

3. Monitorar as Conversões:
- Uma vez configurado, o Google Ads irá coletar dados sobre a eficácia de seus anúncios e como os usuários interagem com o app, incluindo o impacto das campanhas de instalação ou eventos personalizados.
  

  