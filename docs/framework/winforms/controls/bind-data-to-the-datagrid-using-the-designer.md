---
title: "如何：使用设计器将数据绑定到 Windows 窗体的 DataGridView 控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a3c7422bc83c7ee1f09bac05333799708cd2f2f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>如何：使用设计器将数据绑定到 Windows 窗体的 DataGridView 控件
你可以使用设计器连接<xref:System.Windows.Forms.DataGridView>控件添加到数据源的多个不同的类型，包括数据库、 业务对象或 Web 服务。 当将控件绑定到数据源使用设计器中时，控件将自动绑定到<xref:System.Windows.Forms.BindingSource>表示数据源的组件。 此外，会在控件中自动生成列以匹配数据源提供的架构信息。  
  
 生成列后，可根据需要对其进行修改。 例如，可删除或隐藏不不想显示的列、重新排列各列或修改列的类型。 有关修改列的详细信息，请参阅“另请参阅”部分中列出的主题。  
  
 你也可以将绑定多个<xref:System.Windows.Forms.DataGridView>控件添加到相关表来创建主/从关系。 在此配置中，一个控件显示父表，另一个控件只显示子表中与父表中的当前行相关的行。 有关详细信息，请参阅[如何：在 Windows 窗体应用程序中显示相关数据](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)。  
  
 下面的过程需要**Windows 应用程序**具有一个包含窗体项目<xref:System.Windows.Forms.DataGridView>控件或主/从关系的两个控件。 有关启动此类项目的信息，请参阅[如何：创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何：向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-bind-the-control-to-a-data-source"></a>将控件绑定到数据源  
  
1.  单击智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 右上角<xref:System.Windows.Forms.DataGridView>控件。  
  
2.  单击“选择数据源”选项的下拉箭头。  
  
3.  如果项目尚没有数据源，请单击“添加项目数据源”，按照向导指示的步骤进行操作。  
  
     有关详细信息，请参阅[数据源配置向导](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)。 新数据源将显示在“选择数据源”下拉窗口中。 如果新数据源只包含一个成员（例如单个数据库表），控件将自动绑定到该成员。 否则，请记住执行下一步。  
  
4.  如果尚未展开，则展开“其他数据源”和“项目数据源”节点，然后选择绑定控件的数据源。  
  
5.  如果您的数据源包含多个成员，例如，如果你具有创建<xref:System.Data.DataSet?displayProperty=nameWithType>包含多个表，展开数据源，然后选择要绑定到的特定成员。  
  
6.  若要在创建主/从关系，**选择数据源**第二个下拉窗口<xref:System.Windows.Forms.DataGridView>控件中，展开<xref:System.Windows.Forms.BindingSource>为父表中，创建，然后从列表中选择相关的子表所示。  
  
    > [!NOTE]
    >  如果项目已有数据源，还可以使用“数据源”窗口创建数据窗体。 有关详细信息，请参阅[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 [如何：连接到数据库中的数据](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)  
 [如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和删除列](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [如何：使用设计器更改 Windows 窗体 DataGridView 控件中的列顺序](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 [如何：使用设计器更改 Windows 窗体 DataGridView 列类型](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 [如何：使用设计器在 Windows 窗体 DataGridView 控件中冻结列](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 [如何：使用设计器在 Windows 窗体 DataGridView 控件中隐藏列](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 [如何：使用设计器在 Windows 窗体 DataGridView 控件中将列设为只读](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 [如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [如何：向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)  
 [如何：在 Windows 窗体应用程序中显示相关数据](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
