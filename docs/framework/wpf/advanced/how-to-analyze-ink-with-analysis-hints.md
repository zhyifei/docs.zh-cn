---
title: "如何：通过分析提示来分析墨迹"
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
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b97f7fe0314b6bf839e4e639e32a48f9261def73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a><span data-ttu-id="1d214-102">如何：通过分析提示来分析墨迹</span><span class="sxs-lookup"><span data-stu-id="1d214-102">How to: Analyze Ink with Analysis Hints</span></span>
<span data-ttu-id="1d214-103">[System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx)提供提示[System.Windows.Ink.InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx)它所附加到。</span><span class="sxs-lookup"><span data-stu-id="1d214-103">An [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) provides a hint for the [System.Windows.Ink.InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx) to which it is attached.</span></span>  <span data-ttu-id="1d214-104">提示适用于指定的区域[System.Windows.Ink.ContextNode.Location%2A](https://msdn.microsoft.com/library/system.windows.ink.contextnode.location(v=vs.100).aspx)属性[System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx)并提供到墨迹分析器的额外上下文提高识别的准确性。</span><span class="sxs-lookup"><span data-stu-id="1d214-104">The hint applies to the area specified by the [System.Windows.Ink.ContextNode.Location%2A](https://msdn.microsoft.com/library/system.windows.ink.contextnode.location(v=vs.100).aspx) property of the [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) and provides extra context to the ink analyzer to improve recognition accuracy.</span></span> <span data-ttu-id="1d214-105">[System.Windows.Ink.InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx)提示的区域内，从分析墨迹获得时应用此上下文信息。</span><span class="sxs-lookup"><span data-stu-id="1d214-105">The [System.Windows.Ink.InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx) applies this context information when analyzing ink obtained from within the hint's area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d214-106">示例</span><span class="sxs-lookup"><span data-stu-id="1d214-106">Example</span></span>  
 <span data-ttu-id="1d214-107">下面的示例是使用多个应用程序[System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx)接受墨迹输入的窗体上的对象。</span><span class="sxs-lookup"><span data-stu-id="1d214-107">The following example is an application that uses multiple [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) objects on a form that accepts ink input.</span></span> <span data-ttu-id="1d214-108">应用程序使用[System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode.factoid(v=vs.100))属性，以提供窗体上的每个条目的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="1d214-108">The application uses the [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode.factoid(v=vs.100)) property to provide context information for each entry on the form.</span></span>  <span data-ttu-id="1d214-109">应用程序使用背景分析来分析墨迹并清除所有墨迹形式 5 秒后用户停止添加墨迹。</span><span class="sxs-lookup"><span data-stu-id="1d214-109">The application uses background analysis to analyze the ink and clears the form of all ink five seconds after the user stops adding ink.</span></span>  
  
 [!code-xaml[HowToAnalyzeInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
