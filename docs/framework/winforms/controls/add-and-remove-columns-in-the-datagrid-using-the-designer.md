---
title: "如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b314fe58413c0a284f5ebb41642e8c8dd1fb02b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列
Windows 窗体<xref:System.Windows.Forms.DataGridView>控件必须包含才能显示数据的列。 如果你计划手动填充该控件，你必须自己添加列。 或者，你可以将控件绑定到数据源，也不能生成自动填充列。 如果数据源包含多于你想要显示的列数，则可以删除不需要的列。  
  
 下面的过程要求**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.DataGridView>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-add-a-column-using-the-designer"></a>若要添加使用设计器的列  
  
1.  单击智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 右上角<xref:System.Windows.Forms.DataGridView>控制，，然后选择**添加列**。  
  
2.  在**添加列**对话框框中，选择**数据绑定列**选项和从数据源中，选择一列或选择**未绑定列**选项和定义列使用提供的字段。  
  
3.  单击**添加**按钮以添加列，使其出现在设计器中的现有列不能已填充控件显示区域时。  
  
    > [!NOTE]
    >  你可以修改中的列属性**编辑列**对话框中，你可以访问从控件的智能标记。  
  
### <a name="to-remove-a-column-using-the-designer"></a>若要删除某一列使用设计器  
  
1.  选择**编辑列**从控件的智能标记。  
  
2.  选择从列**选定的列**列表。  
  
3.  单击**删除**按钮以删除列，使其从设计器中消失。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 [如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [如何：向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
