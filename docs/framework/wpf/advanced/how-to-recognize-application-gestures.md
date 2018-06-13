---
title: 如何：识别应用程序操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 82ca91fc9e3745012d82357991b67f398079f1f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543688"
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="ac7dd-102">如何：识别应用程序操作</span><span class="sxs-lookup"><span data-stu-id="ac7dd-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="ac7dd-103">下面的示例演示埃墨迹，当用户进行<xref:System.Windows.Ink.ApplicationGesture.ScratchOut>笔势上<xref:System.Windows.Controls.InkCanvas>。</span><span class="sxs-lookup"><span data-stu-id="ac7dd-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="ac7dd-104">此示例假定<xref:System.Windows.Controls.InkCanvas>、 调用`inkCanvas1`，XAML 文件中声明。</span><span class="sxs-lookup"><span data-stu-id="ac7dd-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac7dd-105">示例</span><span class="sxs-lookup"><span data-stu-id="ac7dd-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ac7dd-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac7dd-106">See Also</span></span>  
 <xref:System.Windows.Ink.ApplicationGesture>  
 <xref:System.Windows.Controls.InkCanvas>  
 <xref:System.Windows.Controls.InkCanvas.Gesture>
