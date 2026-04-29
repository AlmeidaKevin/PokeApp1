
# 📱 PokeApp

Aplicación móvil desarrollada con Ionic + Capacitor.

## 🚀 Instalación

Clona el repositorio:

```bash
git clone https://github.com/AlmeidaKevin/PokeApp1.git
cd PokeApp1
```

Instala las dependencias:

```bash
npm install
```

---

## ⚙️ Configuración de Splash Screen

### 1. Instalar plugin

```bash
npm install @capacitor/splash-screen
```

---

### 2. Configurar `capacitor.config.ts`

```ts
plugins: {
  SplashScreen: {
    launchShowDuration: 0,
    launchAutoHide: true,
    backgroundColor: "#ffffffff",
    androidSplashResourceName: "splash",
    androidScaleType: "CENTER_CROP",
    showSpinner: false,
    androidSpinnerStyle: "large",
    iosSpinnerStyle: "small",
    spinnerColor: "#999999",
    splashFullScreen: false,
    splashImmersive: false,
    layoutName: "launch_screen",
    useDialog: false,
  },
},
```

---

### 3. Configurar `app.component.ts`

```ts
import { SplashScreen } from '@capacitor/splash-screen';

export class AppComponent {
  constructor() {
    this.showSplash();
  };

  async showSplash(){
    await SplashScreen.show({
      autoHide: true,
      showDuration: 3000
    });
  }
}
```

---

## 🤖 Configuración para Android

### 1. Instalar plataforma Android

```bash
npm i @capacitor/android
```

```bash
ionic build
```

```bash
npx cap add android
```

---

## 🎨 Configuración de Iconos y Splash Assets

### 1. Instalar herramienta

```bash
npm install @capacitor/assets
```

O como dependencia de desarrollo:

```bash
npm install @capacitor/assets --save-dev
```

---

### 2. Estructura de archivos

Ubica tus imágenes en la carpeta `assets/`:

```
assets/
├── icon-only.png
├── icon-foreground.png
├── icon-background.png
├── splash.png
└── splash-dark.png
```

📌 Requisitos:

* Iconos: mínimo **1024x1024 px**
* Splash: mínimo **2732x2732 px**
* Formato: **PNG o JPG**

---

### 3. Generar assets

```bash
npx capacitor-assets generate
```

---

### 4. Abrir Android Studio

```bash
npx cap open android
```

---

### 5. Configurar estilos (IMPORTANTE)

Editar:

```
android/app/src/main/res/values/styles.xml
```

Reemplazar:

```xml
<style name="AppTheme.NoActionBarLaunch" parent="Theme.SplashScreen">
    <item name="android:background">@drawable/splash</item>
</style>
```

Por:

```xml
<style name="AppTheme.NoActionBarLaunch" parent="AppTheme.NoActionBar">
    <item name="android:background">#ffffffff</item>
</style>
```

---

### 6. Sincronizar cambios

```bash
ionic cap sync android
```

---

## 📦 Generar APK

Desde Android Studio:

1. Abrir el proyecto (`npx cap open android`)
2. Ir a **Build > Build APK(s)**
3. Ubicar el archivo generado

---

## 📸 Capturas de pantalla




<p align="center">[LA APLICACION MOVIL CON EL ICON Y EL SPLASH SCREEN]</p>


<p align="center">
    <img width="720" height="400" alt="Imagen 1" src="https://github.com/user-attachments/assets/2c619db8-cb1d-4e41-942b-1ad6125257ca" />
</p>




<p align="center">

  <img width="45%" height="1600" alt="Imagen 2" src="https://github.com/user-attachments/assets/3db3d609-6553-4d86-adcd-66b59e2458e4" />
  <img width="45%" height="1600" alt="Imagen 3" src="https://github.com/user-attachments/assets/a55a74e3-8428-4fbd-82f5-4541d8402ad5" />
  <img width="45%" height="1600" alt="Imagen 4" src="https://github.com/user-attachments/assets/af4efa78-f036-4f86-b512-225320420e64" />
  <img width="45%" height="1600" alt="Imagen 5" src="https://github.com/user-attachments/assets/68c055d4-d01d-4684-90c5-4987b895c559" />
  <img width="45%" height="1600" alt="Imagen 6" src="https://github.com/user-attachments/assets/e11080ac-e110-4e98-8b1a-1d6704a77234" />
  <img width="45%" height="1600" alt="Imagen 7" src="https://github.com/user-attachments/assets/4d8a2c0e-04d3-4496-85b0-ec585ced0a2c" />

</p>



---

## ✅ Notas

* Asegúrate de ejecutar `ionic build` antes de sincronizar cambios.
* Si modificas assets o configuración, vuelve a ejecutar:

```bash
ionic cap sync android
```
