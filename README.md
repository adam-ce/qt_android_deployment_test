# steps to reproduce
1. clone
2. open in qt creator
3. select android target (`arm64-v8a` and `armeabi-v7a` tested)
4. select `main1` target and run (it'll compile before running)
5. see that it runs fine, "hello from main1.cpp (42)" is printed
6. select `submain` target and run. either nothing happens or the below error is printed

```
I example.submai: Late-enabling -Xcheck:jni
I Perf    : Connecting to perf service.
W System  : ClassLoader referenced unknown path:
W example.submai: Accessing hidden method Landroid/content/ContextWrapper;->getDisplay()Landroid/view/Display; (light greylist, linking)
I DecorView: It non-support bigbang
I PhoneWindow: generateLayout isLightNavi false, Visibility: 0
D OpenGLRenderer: Skia GL Pipeline
E AndroidRuntime: FATAL EXCEPTION: qtMainLoopThread
E AndroidRuntime: Process: org.qtproject.example.submain, PID: 3725
E AndroidRuntime: java.lang.UnsatisfiedLinkError: dlopen failed: library "ld-android.so" not found
E AndroidRuntime: 	at java.lang.Runtime.load0(Runtime.java:928)
E AndroidRuntime: 	at java.lang.System.load(System.java:1633)
E AndroidRuntime: 	at org.qtproject.qt.android.QtNative$2.run(QtNative.java:229)
E AndroidRuntime: 	at org.qtproject.qt.android.QtThread$2.run(QtThread.java:51)
E AndroidRuntime: 	at org.qtproject.qt.android.QtThread$1.run(QtThread.java:25)
E AndroidRuntime: 	at java.lang.Thread.run(Thread.java:764)
I Process : Sending signal. PID: 3725 SIG: 9
```
