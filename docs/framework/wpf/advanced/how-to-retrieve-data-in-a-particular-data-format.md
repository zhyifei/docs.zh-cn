---
title: 如何：以特定数据格式检索数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: d11374cbc70210e648e93a385c4a9fbca112c09f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718284"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="257cf-102">如何：以特定数据格式检索数据</span><span class="sxs-lookup"><span data-stu-id="257cf-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="257cf-103">以下示例演示如何从指定的格式中的数据对象中检索数据。</span><span class="sxs-lookup"><span data-stu-id="257cf-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="257cf-104">示例</span><span class="sxs-lookup"><span data-stu-id="257cf-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="257cf-105">描述</span><span class="sxs-lookup"><span data-stu-id="257cf-105">Description</span></span>  
 <span data-ttu-id="257cf-106">下面的代码示例使用<xref:System.Windows.DataObject.GetDataPresent%28System.String%29>重载，以首先检查是否指定的数据格式 （本机或通过自动转换）; 如果指定的格式不可用，该示例通过检索数据<xref:System.Windows.DataObject.GetData%28System.String%29>方法。</span><span class="sxs-lookup"><span data-stu-id="257cf-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="257cf-107">代码</span><span class="sxs-lookup"><span data-stu-id="257cf-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="257cf-108">示例</span><span class="sxs-lookup"><span data-stu-id="257cf-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="257cf-109">描述</span><span class="sxs-lookup"><span data-stu-id="257cf-109">Description</span></span>  
 <span data-ttu-id="257cf-110">下面的示例代码使用<xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29>重载来首先检查指定的数据格式是否可用本机 （自动转换的数据格式已筛选的）; 如果指定的格式不可用，该示例通过使用检索数据<xref:System.Windows.DataObject.GetData%28System.String%29>方法。</span><span class="sxs-lookup"><span data-stu-id="257cf-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="257cf-111">代码</span><span class="sxs-lookup"><span data-stu-id="257cf-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="257cf-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="257cf-112">See also</span></span>
- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="257cf-113">拖放概述</span><span class="sxs-lookup"><span data-stu-id="257cf-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
