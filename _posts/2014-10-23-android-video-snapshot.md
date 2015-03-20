---
layout: post
title: Android得到视频缩略图
date: 2014-10-23 21:34
categories: Android
tags: video
excerpt: Android得到视频缩略图
---

Android得到视频缩略图，可以通过接口类 MediaMetadataRetriever 来实现

具体可以看代码

```java
public Bitmap getVideoThumbnail(String filePath) {
            Bitmap bitmap = null;
            MediaMetadataRetriever retriever = new MediaMetadataRetriever();
            try {
                retriever.setDataSource(filePath);
                bitmap = retriever.getFrameAtTime();
            } 
            catch(IllegalArgumentException e) {
                e.printStackTrace();
            } 
            catch (RuntimeException e) {
                e.printStackTrace();
            } 
            finally {
                try {
                    retriever.release();
                } 
                catch (RuntimeException e) {
                    e.printStackTrace();
                }
            }
            return bitmap;
}
```java

其中函数getFrameAtTime()有其他重载函数，该函数会随机选择一帧抓取，如果想要指定具体时间的缩略图，可以用函数getFrameAtTime(long timeUs), getFrameAtTime(long timeUs, int option)，具体如何使用可以查doc。
