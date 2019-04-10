---
title: 存储墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
ms.openlocfilehash: 4089aa7942105c14eb628c75edb7f53ffacfaeb0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182333"
---
# <a name="storing-ink"></a><span data-ttu-id="349eb-102">存储墨迹</span><span class="sxs-lookup"><span data-stu-id="349eb-102">Storing Ink</span></span>
<span data-ttu-id="349eb-103"><xref:System.Windows.Ink.StrokeCollection.Save%2A>方法来存储墨迹作为墨迹序列化格式 (ISF) 提供支持。</span><span class="sxs-lookup"><span data-stu-id="349eb-103">The <xref:System.Windows.Ink.StrokeCollection.Save%2A> methods provide support for storing ink as Ink Serialized Format (ISF).</span></span> <span data-ttu-id="349eb-104">构造函数<xref:System.Windows.Ink.StrokeCollection>类用于读取墨迹数据提供支持。</span><span class="sxs-lookup"><span data-stu-id="349eb-104">Constructors for the <xref:System.Windows.Ink.StrokeCollection> class provide support for reading ink data.</span></span>  
  
## <a name="ink-storage-and-retrieval"></a><span data-ttu-id="349eb-105">手写内容存储和检索</span><span class="sxs-lookup"><span data-stu-id="349eb-105">Ink Storage and Retrieval</span></span>  
 <span data-ttu-id="349eb-106">本部分讨论如何存储和检索中的墨迹[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]平台。</span><span class="sxs-lookup"><span data-stu-id="349eb-106">This section discusses how to store and retrieve ink in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] platform.</span></span>  
  
 <span data-ttu-id="349eb-107">下面的示例实现一个按钮单击事件处理程序，向用户呈现一个保存文件对话框，并将从手写内容保存<xref:System.Windows.Controls.InkCanvas>扩展到一个文件。</span><span class="sxs-lookup"><span data-stu-id="349eb-107">The following example implements a button-click event handler that presents the user with a File Save dialog box and saves the ink from an <xref:System.Windows.Controls.InkCanvas> out to a file.</span></span>  
  
 [!code-csharp[DigitalInkTopics#12](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 <span data-ttu-id="349eb-108">下面的示例实现一个按钮单击事件处理程序，向用户呈现一个文件打开对话框并从到的文件中读取墨迹<xref:System.Windows.Controls.InkCanvas>元素。</span><span class="sxs-lookup"><span data-stu-id="349eb-108">The following example implements a button-click event handler that presents the user with a File Open dialog box and reads ink from the file into an <xref:System.Windows.Controls.InkCanvas> element.</span></span>  
  
 [!code-csharp[DigitalInkTopics#13](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="349eb-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="349eb-109">See also</span></span>

- <xref:System.Windows.Controls.InkCanvas>
- [<span data-ttu-id="349eb-110">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="349eb-110">Windows Presentation Foundation</span></span>](../index.md)
