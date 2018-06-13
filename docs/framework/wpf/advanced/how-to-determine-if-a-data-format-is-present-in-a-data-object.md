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
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a>如何：确定数据格式是否存在于数据对象中
下面的示例演示如何使用各种<xref:System.Windows.DataObject.GetDataPresent%2A>方法重载来查询特定的数据格式是否存在数据对象中。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的代码示例使用<xref:System.Windows.DataObject.GetDataPresent%28System.String%29>查询是否存在特定的数据格式由描述符字符串的重载。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的代码示例使用<xref:System.Windows.DataObject.GetDataPresent%28System.Type%29>查询是否存在特定的数据格式由类型的重载。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的代码示例使用<xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29>重载查询数据由描述符字符串，并指定如何处理自动转换的数据格式。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.IDataObject>
