# PC Controller Pro — Mobile App (Android APK)

Все файлы мобильного приложения расположены на **Диске D**: `D:\TelegramMobileApp`. На Диск С ничего не устанавливалось.

## Сборка Android APK (`.apk`)

1. Установите [Android Studio](https://developer.android.com/studio) (при установке укажите путь на Диск D, если требуется).
2. Откройте терминал в папке `D:\TelegramMobileApp` и выполните установку зависимостей:
   ```bash
   npm install
   ```
3. Инициализируйте Android проект Capacitor:
   ```bash
   npx cap add android
   ```
4. Соберите отладочный `.apk` файл:
   ```bash
   npx cap sync android
   cd android
   ./gradlew assembleDebug
   ```
   Готовый `.apk` файл появится по пути:  
   `D:\TelegramMobileApp\android\app\build\outputs\apk\debug\app-debug.apk`

---

## 🍏 Почему нельзя собрать `.ipa` (iOS) на Windows?
Компания Apple на уровне операционной системы установила жесткое ограничение: **сборка `.ipa` файлов для iPhone и iPad возможна исключительно в среде macOS с установленной программой Xcode**. На компьютерах под управлением Windows физически невозможно скомпилировать iOS-приложение. Для пользователей iPhone предусмотрен запуск через официальный Telegram Web App (внутри самого Telegram без установки сторонних файлов).

---

## 🔄 Система авто-обновления
В приложении реализована проверка версии (`version.json`). Когда вы обновляете бэкенд или веб-интерфейс, приложение проверяет актуальную версию и предлагает пользователю обновиться в один клик.
