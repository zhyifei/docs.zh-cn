---
title: 如何：在数据对象中存储多种数据格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], storing multiple formats
- DataFormats class [WPF], storing multiple formats
- drag-and-drop [WPF], storing multiple formats
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
ms.openlocfilehash: e47d0aa2fe1c573314551ad91a2199ca97fd61a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543463"
---
# <a name="how-to-store-multiple-data-formats-in-a-data-object"></a><span data-ttu-id="fdcf9-102">如何：在数据对象中存储多种数据格式</span><span class="sxs-lookup"><span data-stu-id="fdcf9-102">How to: Store Multiple Data Formats in a Data Object</span></span>
<span data-ttu-id="fdcf9-103">下面的示例演示如何使用<xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29>方法将数据添加到多个格式中的数据对象。</span><span class="sxs-lookup"><span data-stu-id="fdcf9-103">The following example shows how to use the <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> method to add data to a data object in multiple formats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdcf9-104">示例</span><span class="sxs-lookup"><span data-stu-id="fdcf9-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="fdcf9-105">描述</span><span class="sxs-lookup"><span data-stu-id="fdcf9-105">Description</span></span>  
  
### <a name="code"></a><span data-ttu-id="fdcf9-106">代码</span><span class="sxs-lookup"><span data-stu-id="fdcf9-106">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## <a name="see-also"></a><span data-ttu-id="fdcf9-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdcf9-107">See Also</span></span>  
 <xref:System.Windows.IDataObject>  
 [<span data-ttu-id="fdcf9-108">拖放概述</span><span class="sxs-lookup"><span data-stu-id="fdcf9-108">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
