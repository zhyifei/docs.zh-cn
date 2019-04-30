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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053362"
---
# <a name="storing-ink"></a>存储墨迹
<xref:System.Windows.Ink.StrokeCollection.Save%2A>方法来存储墨迹作为墨迹序列化格式 (ISF) 提供支持。 构造函数<xref:System.Windows.Ink.StrokeCollection>类用于读取墨迹数据提供支持。  
  
## <a name="ink-storage-and-retrieval"></a>手写内容存储和检索  
 本部分讨论如何存储和检索中的墨迹[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]平台。  
  
 下面的示例实现一个按钮单击事件处理程序，向用户呈现一个保存文件对话框，并将从手写内容保存<xref:System.Windows.Controls.InkCanvas>扩展到一个文件。  
  
 [!code-csharp[DigitalInkTopics#12](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 下面的示例实现一个按钮单击事件处理程序，向用户呈现一个文件打开对话框并从到的文件中读取墨迹<xref:System.Windows.Controls.InkCanvas>元素。  
  
 [!code-csharp[DigitalInkTopics#13](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.InkCanvas>
- [Windows Presentation Foundation](../index.md)
