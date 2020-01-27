---
title: 如何：提取与文件关联的图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742540"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>如何：提取与 Windows 窗体中的文件关联的图标
许多文件都具有嵌入的图标，可提供相关文件类型的直观表示形式。 例如，Microsoft Word 文档包含一个图标，该图标将其标识为 Word 文档。 当在列表控件或表控件中显示文件时，您可能希望显示表示每个文件名旁边的文件类型的图标。 可以通过使用 <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> 方法轻松实现此目的。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何提取与文件关联的图标，并在 <xref:System.Windows.Forms.ListView> 控件中显示文件名及其关联的图标。  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 若要编译该示例：  
  
- 将前面的代码粘贴到 Windows 窗体中，并从窗体的构造函数或 <xref:System.Windows.Forms.Form.Load> 事件处理方法中调用 `ExtractAssociatedIconExample` 方法。  
  
     你将需要确保你的窗体导入 <xref:System.IO> 命名空间。  
  
## <a name="see-also"></a>另请参阅

- [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
- [ListView 控件](../controls/listview-control-windows-forms.md)
