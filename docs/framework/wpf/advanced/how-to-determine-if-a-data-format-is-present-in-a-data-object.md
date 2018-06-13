---
title: 如何：确定数据格式是否存在于数据对象中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
ms.openlocfilehash: e3e2f47df0ae1fdf0fe875827473f2c3a1b53fb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543414"
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="9b7d3-102">如何：确定数据格式是否存在于数据对象中</span><span class="sxs-lookup"><span data-stu-id="9b7d3-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="9b7d3-103">下面的示例演示如何使用各种<xref:System.Windows.DataObject.GetDataPresent%2A>方法重载来查询特定的数据格式是否存在数据对象中。</span><span class="sxs-lookup"><span data-stu-id="9b7d3-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b7d3-104">示例</span><span class="sxs-lookup"><span data-stu-id="9b7d3-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9b7d3-105">描述</span><span class="sxs-lookup"><span data-stu-id="9b7d3-105">Description</span></span>  
 <span data-ttu-id="9b7d3-106">下面的代码示例使用<xref:System.Windows.DataObject.GetDataPresent%28System.String%29>查询是否存在特定的数据格式由描述符字符串的重载。</span><span class="sxs-lookup"><span data-stu-id="9b7d3-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9b7d3-107">代码</span><span class="sxs-lookup"><span data-stu-id="9b7d3-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="9b7d3-108">示例</span><span class="sxs-lookup"><span data-stu-id="9b7d3-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9b7d3-109">描述</span><span class="sxs-lookup"><span data-stu-id="9b7d3-109">Description</span></span>  
 <span data-ttu-id="9b7d3-110">下面的代码示例使用<xref:System.Windows.DataObject.GetDataPresent%28System.Type%29>查询是否存在特定的数据格式由类型的重载。</span><span class="sxs-lookup"><span data-stu-id="9b7d3-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9b7d3-111">代码</span><span class="sxs-lookup"><span data-stu-id="9b7d3-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="9b7d3-112">示例</span><span class="sxs-lookup"><span data-stu-id="9b7d3-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9b7d3-113">描述</span><span class="sxs-lookup"><span data-stu-id="9b7d3-113">Description</span></span>  
 <span data-ttu-id="9b7d3-114">下面的代码示例使用<xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29>重载查询数据由描述符字符串，并指定如何处理自动转换的数据格式。</span><span class="sxs-lookup"><span data-stu-id="9b7d3-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9b7d3-115">代码</span><span class="sxs-lookup"><span data-stu-id="9b7d3-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="9b7d3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b7d3-116">See Also</span></span>  
 <xref:System.Windows.IDataObject>
