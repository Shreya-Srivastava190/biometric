Datalake Biometrics is an offline-first, edge facial recognition terminal. Built with React Native and a custom Kotlin ML bridge, it processes identities locally via TFLite and SQLite for zero-latency authentication. It seamlessly background-syncs encrypted attendance logs with a Supabase PostgreSQL cloud when connectivity returns.

👁️ Datalake Biometrics: Edge-First Identity Vault
React Native Kotlin SQLite Supabase

Traditional cloud-dependent biometric systems suffer from latency, privacy risks, and complete failure in low-connectivity environments like remote field sites or factory floors.

Datalake Biometrics is an offline-first, edge-computing facial recognition terminal built to solve this. It processes identities entirely on-device, ensuring zero-latency authentication, operational resilience, and maximum data privacy.

🚀 Quick Start: Try the App
Due to platform submission limits (25MB), the node_modules and heavy Android build artifacts have been omitted from this repository source code.

To test the application immediately without compiling from source, please download the pre-built Release APK:

👉 DOWNLOAD RELEASE APK HERE

Note: Ensure "Install from Unknown Sources" is enabled on your Android device to test the APK.

✨ Key Features
⚡ Zero-Latency Verification: Authenticates identities in milliseconds against a local SQLite vault. Requires zero active internet connection to function.
🧠 Custom Kotlin ML Bridge: A high-performance bridge between Android's CameraX and React Native prevents frame drops and UI thread blocking during active ML inference.
🔄 Offline-First Sync Engine: Automatically pushes encrypted attendance logs and fetches new master identities whenever a network is detected in the background.
💻 Enterprise Telemetry UI: A floating terminal interface providing real-time liveness detection, network state, and system logs.
⚙️ Hardware Kiosk Ready: Includes bilingual support (English/Hindi) and an SQLite-persisted Dark/Light theme tailored for dedicated hardware deployments.
🛠️ Technical Architecture
Instead of transmitting raw images to a vulnerable cloud server, our custom Kotlin native module leverages a lightweight (4MB) MobileFaceNet TFLite model to generate encrypted mathematical face vectors.

These vectors are securely persisted in a local SQLite database. When network connectivity is restored, a background worker seamlessly syncs attendance logs and roster updates with a Supabase PostgreSQL backend without interrupting the active camera feed.

Frontend: React Native (TypeScript/JavaScript)
Native ML Layer: Kotlin, Android CameraX, TensorFlow Lite
Edge Storage: react-native-quick-sqlite
Cloud Infrastructure: Supabase (PostgreSQL)
💻 Local Development & Installation
If you wish to build the project from the source code, follow these steps:

1. Prerequisites
Node.js (v18 or newer)
Android Studio & Android SDK (Ensure NDK and CMake are installed for the native Kotlin bridge)
React Native CLI
A physical Android device connected via USB (with USB Debugging enabled) or an Emulator with camera support.
