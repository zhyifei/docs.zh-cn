---
title: 如何：向 WPF 应用程序添加初始屏幕
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 3120ee64d65822d323800a89466c6b707169aaaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307465"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>如何：向 WPF 应用程序添加初始屏幕

本主题演示如何将添加一个启动窗口中，或*初始屏幕*，到 Windows Presentation Foundation (WPF) 应用程序。

## <a name="to-add-an-existing-image-as-a-splash-screen"></a>若要将现有映像添加为初始屏幕

1. 创建或查找想要用于初始屏幕的图像。 可以使用任何支持的 Windows Imaging Component (WIC) 的图像格式。 例如，可以使用 BMP、 GIF、 JPEG、 PNG 或 TIFF 格式。

2. 将图像文件添加到 WPF 应用程序项目。

3. 在中**解决方案资源管理器**，选择的映像。

4. 在属性窗口中，单击下拉箭头**生成操作**属性。

5. 选择**初始屏幕**从下拉列表。

6. 按 F5 生成并运行该应用程序。

     初始屏幕图像显示在屏幕上，在中心，然后淡主应用程序窗口出现时。

## <a name="to-exclude-the-splash-screen-from-build"></a>若要从生成中排除的初始屏幕

1. 在中**解决方案资源管理器**，选择初始屏幕图像。

2. 在中**属性**窗口中，将**生成操作**到**None**。

## <a name="to-remove-the-splash-screen-from-an-application"></a>若要删除从应用程序的初始屏幕

在中**解决方案资源管理器**，删除初始屏幕图像。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.SplashScreen>
- [如何：向项目添加现有项](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
