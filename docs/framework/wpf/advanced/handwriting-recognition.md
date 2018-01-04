---
title: "手写识别"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 384f21587c29e6afe82964fc28432f5a6be92b05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="handwriting-recognition"></a><span data-ttu-id="337b9-102">手写识别</span><span class="sxs-lookup"><span data-stu-id="337b9-102">Handwriting Recognition</span></span>
<span data-ttu-id="337b9-103">本节介绍了识别基础知识，因为这与 WPF 平台中数字墨迹有关。</span><span class="sxs-lookup"><span data-stu-id="337b9-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="337b9-104">识别解决方案</span><span class="sxs-lookup"><span data-stu-id="337b9-104">Recognition Solutions</span></span>  
 <span data-ttu-id="337b9-105">以下示例演示如何使用 [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx) 类识别墨迹。</span><span class="sxs-lookup"><span data-stu-id="337b9-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx) class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="337b9-106">此示例要求在系统上安装手写识别器。</span><span class="sxs-lookup"><span data-stu-id="337b9-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="337b9-107">在 Visual Studio 中创建一个名为 **InkRecognition** 的新 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="337b9-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="337b9-108">用下列 XAML 代码替换 Window1.xaml 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="337b9-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="337b9-109">此代码呈现应用程序的用户界面。</span><span class="sxs-lookup"><span data-stu-id="337b9-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="337b9-110">添加对 Microsoft 墨迹程序集和 Microsoft.Ink.dll 的引用，可在 \Program Files\Common Files\Microsoft Shared\Ink 中找到这些内容。</span><span class="sxs-lookup"><span data-stu-id="337b9-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="337b9-111">用下列代码替换代码隐藏文件的内容。</span><span class="sxs-lookup"><span data-stu-id="337b9-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="337b9-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="337b9-112">See Also</span></span>  
 <span data-ttu-id="337b9-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span><span class="sxs-lookup"><span data-stu-id="337b9-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span></span>
