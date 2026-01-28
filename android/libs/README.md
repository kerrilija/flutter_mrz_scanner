# Cached Dependencies

These are backup copies of the Maven dependencies in case the remote repositories become unavailable.

## Files

- `fotoapparat-2.7.0.aar` - Camera library from Appodeal artifactory
- `fotoapparat-2.7.0.pom` - POM file for fotoapparat
- `tesseract4android-4.9.0.aar` - OCR library from JitPack
- `tesseract4android-4.9.0.pom` - POM file for tesseract4android

## Important Note

JitPack doesn't have pre-built artifacts for tesseract4android. The AAR file was extracted from the Gradle cache after a successful build. If you need to rebuild and the remote URLs fail, you may need to:

1. Find someone who has a successful build
2. Extract from their Gradle cache: `~/.gradle/caches/modules-2/files-2.1/com.github.adaptech-cz.Tesseract4Android/tesseract4android/4.9.0/*/tesseract4android-4.9.0.aar`

## How to Use Local Dependencies

If remote repositories fail, modify `build.gradle` to use local files:

```gradle
repositories {
    flatDir {
        dirs 'libs'
    }
    // ... other repos
}

dependencies {
    implementation(name: 'fotoapparat-2.7.0', ext: 'aar')
    implementation(name: 'tesseract4android-4.9.0', ext: 'aar')
}
```

## Current Remote Sources

- fotoapparat: `https://artifactory.appodeal.com/appodeal-public/io/fotoapparat/fotoapparat/2.7.0/`
- tesseract4android: `https://jitpack.io/com/github/adaptech-cz/Tesseract4Android/4.9.0/`
