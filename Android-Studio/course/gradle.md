## module gradle

```gradle
apply plugin: 'com.android.application'

android {
    compileSdkVersion 25
    buildToolsVersion "25.0.3"

    defaultConfig {
        applicationId "com.jackchan.processorsample"
        minSdkVersion 14
        targetSdkVersion 25
        versionCode 1
        versionName "1.0"

        testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"
        
        jackOptions{
            enabled true
        }

    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }

    compileOptions { // 配置jdk版本
        targetCompatibility JavaVersion.VERSION_1_7
        sourceCompatibility = JavaVersion.VERSION_1_7
    }
}

// 错误 编码GBK的不可映射字符
tasks.withType(JavaCompile) {
    options.encoding = "UTF-8"
}

dependencies {
    compile fileTree(include: ['*.jar'], dir: 'libs')
    androidTestCompile('com.android.support.test.espresso:espresso-core:2.2.2', {
        exclude group: 'com.android.support', module: 'support-annotations'
    })
    compile 'com.android.support:appcompat-v7:25.3.1'
}
```