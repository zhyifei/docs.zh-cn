---
title: "如何：列出数据对象中的数据格式"
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
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ef5657aefdf1c229b4f1749881cce1148435a8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="51404-102">如何：列出数据对象中的数据格式</span><span class="sxs-lookup"><span data-stu-id="51404-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="51404-103">下面的示例演示如何使用<xref:System.Windows.DataObject.GetFormats%2A>方法重载获取一个表示每个可用数据对象中的数据格式的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="51404-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51404-104">示例</span><span class="sxs-lookup"><span data-stu-id="51404-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="51404-105">描述</span><span class="sxs-lookup"><span data-stu-id="51404-105">Description</span></span>  
 <span data-ttu-id="51404-106">下面的代码示例使用<xref:System.Windows.DataObject.GetFormats%2A>重载获取表示所有可用数据对象 （本机和自动转换） 中的数据格式的字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="51404-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="51404-107">代码</span><span class="sxs-lookup"><span data-stu-id="51404-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="51404-108">示例</span><span class="sxs-lookup"><span data-stu-id="51404-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="51404-109">描述</span><span class="sxs-lookup"><span data-stu-id="51404-109">Description</span></span>  
 <span data-ttu-id="51404-110">下面的代码示例使用<xref:System.Windows.DataObject.GetFormats%2A>重载获取表示仅数据格式数据对象 （自动转换的数据格式进行筛选） 中可用的字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="51404-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="51404-111">代码</span><span class="sxs-lookup"><span data-stu-id="51404-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="51404-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51404-112">See Also</span></span>  
 <xref:System.Windows.IDataObject>  
 [<span data-ttu-id="51404-113">拖放概述</span><span class="sxs-lookup"><span data-stu-id="51404-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
