---
title: "如何：将初始屏幕添加到 WPF 应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 973f35f6bfa259490a9423bf0b69d676ad968372
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>如何：将初始屏幕添加到 WPF 应用程序
本主题演示如何将添加一个启动窗口中，或*初始屏幕*，到 Windows Presentation Foundation (WPF) 应用程序。  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a>若要将现有映像添加为初始屏幕  
  
1.  创建或查找你想要用于初始屏幕的映像。 你可以使用任何图像格式受支持的 Windows 映像组件 (WIC)。 例如，你可以使用 BMP、 GIF、 JPEG、 PNG 或 TIFF 格式。  
  
2.  将图像文件添加到 WPF 应用程序项目。 有关详细信息，请参阅[NIB： 如何： 将现有项目添加到项目](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)。  
  
3.  在解决方案资源管理器，选择映像。  
  
4.  在属性窗口中，单击下拉箭头**生成操作**属性。  
  
5.  选择**初始屏幕**从下拉列表。  
  
    > [!NOTE]
    >  如果看不到**初始屏幕**选项，请务必检查你正在使用[!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]SP1 或更高版本。  
  
6.  按 F5 生成并运行该应用程序。  
  
     初始屏幕图像出现在该屏幕的中心，然后淡主应用程序窗口出现时。  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>若要删除从应用程序的初始屏幕  
  
1.  在解决方案资源管理器，选择初始屏幕图像。  
  
2.  在属性窗口中，设置**生成操作**到**无**。  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>若要删除从应用程序的初始屏幕  
  
-   在解决方案资源管理器，删除初始屏幕图像。  
  
-   从项目中排除初始屏幕图像。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.SplashScreen>  
 [NIB： 如何： 将现有项添加到项目](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
