---
title: 手写识别
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
ms.openlocfilehash: 8f520b80970bfeebdfea01a6c722634efd99ffe7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725384"
---
# <a name="handwriting-recognition"></a>手写识别
本节介绍了识别基础知识，因为这与 WPF 平台中数字墨迹有关。  
  
## <a name="recognition-solutions"></a>识别解决方案  
 以下示例演示如何使用 [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx) 类识别墨迹。  
  
> [!NOTE]
>  此示例要求在系统上安装手写识别器。  
  
 在 Visual Studio 中创建一个名为 **InkRecognition** 的新 WPF 应用程序项目。 用下列 XAML 代码替换 Window1.xaml 文件的内容。 此代码呈现应用程序的用户界面。  
  
 [!code-xaml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 添加对 Microsoft 墨迹程序集和 Microsoft.Ink.dll 的引用，可在 \Program Files\Common Files\Microsoft Shared\Ink 中找到这些内容。 用下列代码替换代码隐藏文件的内容。  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>请参阅
- [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)
