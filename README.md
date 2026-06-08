# 小六壬起卦器

一款简洁的六壬占卜手机 App，支持月日时起课、三数起课、单数起课、随机取数等多种起卦方式，内置 AI 解卦功能。

## 功能特点

- **月日时起课**：输入月份、日期、时辰，自动推算
- **三数起课**：同时输入三个数字起卦
- **单数起课**：输入一个数字起卦
- **随机取数**：输入任意字符组合，系统自动取数
- **AI 解卦**：支持 OpenAI / Anthropic / DeepSeek / 自定义 API
- **公历农历转换**：自动处理历法换算

## 技术栈

- **前端**：原生 HTML + CSS + JavaScript（单文件，约 1089 行）
- **构建工具**：Vite
- **移动端**：Capacitor 7.x → Android APK
- **JDK**：OpenJDK 21（Android 构建必需）

## 本地运行

```bash
# 安装依赖
npm install

# 开发模式
npm run dev

# 构建 Web资源
npm run build
```

##打包 Android APK

```bash
# 添加 Android 平台（如尚未添加）
npx cap add android

# 同步 Web 资源到 Android
npx cap sync android

# 编译 APK
cd android
.\gradlew.bat assembleDebug
```

APK 输出位置：`android/app/build/outputs/apk/debug/app-debug.apk`

## 项目结构

```
├── src/
│   └── index.html          # 完整应用（HTML + CSS + JS）
├── public/                 # 静态资源
├── android/ # Capacitor Android 项目（自动生成）
├── capacitor.config.json   # Capacitor 配置
├── package.json
├── vite.config.ts
└── tsconfig.json
```

## 注意事项

- Android 构建需要 **JDK 21**，JDK 17 无法编译 Capacitor 7.x
- Android SDK 需提前安装，并配置 `ANDROID_HOME` 环境变量
- 首次构建 APK 时 Gradle 会下载约 230MB 的依赖包，请保持网络连接

## License

MIT