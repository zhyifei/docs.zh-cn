---
title: 如何：列出数据对象中的数据格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: 7d96cc7f7327ff7d33cf1147dbae75bc7620e310
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595885"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="7ac46-102">如何：列出数据对象中的数据格式</span><span class="sxs-lookup"><span data-stu-id="7ac46-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="7ac46-103">下面的示例演示如何使用<xref:System.Windows.DataObject.GetFormats%2A>方法重载获取表示可在数据对象中每个数据格式的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="7ac46-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ac46-104">示例</span><span class="sxs-lookup"><span data-stu-id="7ac46-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7ac46-105">描述</span><span class="sxs-lookup"><span data-stu-id="7ac46-105">Description</span></span>  
 <span data-ttu-id="7ac46-106">下面的示例代码使用<xref:System.Windows.DataObject.GetFormats%2A>重载获取表示所有可用数据对象 （本机和可自动转换） 中的数据格式的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="7ac46-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="7ac46-107">代码</span><span class="sxs-lookup"><span data-stu-id="7ac46-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="7ac46-108">示例</span><span class="sxs-lookup"><span data-stu-id="7ac46-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7ac46-109">描述</span><span class="sxs-lookup"><span data-stu-id="7ac46-109">Description</span></span>  
 <span data-ttu-id="7ac46-110">下面的示例代码使用<xref:System.Windows.DataObject.GetFormats%2A>重载获取表示仅在数据对象 （可自动转换数据格式进行筛选） 中可用数据格式的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="7ac46-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="7ac46-111">代码</span><span class="sxs-lookup"><span data-stu-id="7ac46-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="7ac46-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ac46-112">See also</span></span>
- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="7ac46-113">拖放概述</span><span class="sxs-lookup"><span data-stu-id="7ac46-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
