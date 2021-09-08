---
layout: post
title: "JetBrains Apps Start Failed: UI Initialization Failed and Unable to Load Native GTK Libraries"
categories: Linux JetBrains
author: "Muhammad Naufal Hilmy Makarim"
---

If you get an error like this:
```
Internal error. Please refer to https://code.google.com/p/android/issues

com.intellij.ide.plugins.StartupAbortedException: UI initialization failed
    at com.intellij.idea.StartupUtil.lambda$prepareApp$3(StartupUtil.java:194)
    at java.base/java.util.concurrent.CompletableFuture.uniExceptionally(CompletableFuture.java:986)
    at java.base/java.util.concurrent.CompletableFuture$UniExceptionally.tryFire(CompletableFuture.java:970)
    at java.base/java.util.concurrent.CompletableFuture.postComplete(CompletableFuture.java:506)
    at java.base/java.util.concurrent.CompletableFuture.completeExceptionally(CompletableFuture.java:2088)
    at com.intellij.idea.StartupUtil.lambda$scheduleInitUi$8(StartupUtil.java:332)
    at java.desktop/java.awt.event.InvocationEvent.dispatch(InvocationEvent.java:313)
    at java.desktop/java.awt.EventQueue.dispatchEventImpl(EventQueue.java:776)
    at java.desktop/java.awt.EventQueue$4.run(EventQueue.java:727)
    at java.desktop/java.awt.EventQueue$4.run(EventQueue.java:721)
    at java.base/java.security.AccessController.doPrivileged(Native Method)
    at java.base/java.security.ProtectionDomain$JavaSecurityAccessImpl.doIntersectionPrivilege(ProtectionDomain.java:85)
    at java.desktop/java.awt.EventQueue.dispatchEvent(EventQueue.java:746)
    at java.desktop/java.awt.EventDispatchThread.pumpOneEventForFilters(EventDispatchThread.java:203)
    at java.desktop/java.awt.EventDispatchThread.pumpEventsForFilter(EventDispatchThread.java:124)
    at java.desktop/java.awt.EventDispatchThread.pumpEventsForHierarchy(EventDispatchThread.java:113)
    at java.desktop/java.awt.EventDispatchThread.pumpEvents(EventDispatchThread.java:109)
    at java.desktop/java.awt.EventDispatchThread.pumpEvents(EventDispatchThread.java:101)
    at java.desktop/java.awt.EventDispatchThread.run(EventDispatchThread.java:90)
Caused by: java.util.concurrent.CompletionException: java.lang.InternalError: Unable to load native GTK libraries
    at java.base/java.util.concurrent.CompletableFuture.encodeThrowable(CompletableFuture.java:331)
    at java.base/java.util.concurrent.CompletableFuture.completeThrowable(CompletableFuture.java:346)
    at java.base/java.util.concurrent.CompletableFuture$BiRelay.tryFire(CompletableFuture.java:1423)
    ... 16 more
Caused by: java.lang.InternalError: Unable to load native GTK libraries
    at java.desktop/com.sun.java.swing.plaf.gtk.GTKLookAndFeel.initialize(GTKLookAndFeel.java:1422)
    at java.desktop/javax.swing.UIManager.setLookAndFeel(UIManager.java:591)
    at java.desktop/javax.swing.UIManager.setLookAndFeel(UIManager.java:638)
    at com.intellij.util.ui.StartupUiUtil.initDefaultLaF(StartupUiUtil.java:75)
    at com.intellij.idea.StartupUtil.lambda$scheduleInitUi$8(StartupUtil.java:329)
    ... 13 more

-----
Your JRE: 11.0.10+0-b96-7249189 amd64 (JetBrains s.r.o.)
/snap/android-studio/114/android-studio/jre
```

Try to install `libgthread-2.0`. For example in my system:
```
sudo zypper in libgthread-2_0-0
```

<br>
Hope this helps.
