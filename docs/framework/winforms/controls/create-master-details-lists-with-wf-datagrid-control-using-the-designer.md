---
title: 使用设计器通过 DataGrid 控件创建主/详细信息列表
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 0dea3dd88a8c6c2aceb894789ace8ef3b5c83632
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743383"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件将替换功能并将其添加到 <xref:System.Windows.Forms.DataGrid> 控件;但是，如果您选择，则会保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容性和将来使用。 자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하세요.

 如果您的 <xref:System.Data.DataSet> 包含一系列相关表，则您可以使用两个 <xref:System.Windows.Forms.DataGrid> 控件以主-详细信息格式显示数据。 一个 <xref:System.Windows.Forms.DataGrid> 指定为主网格，第二个指定为详细信息网格。 当你在 "主列表" 中选择条目时，所有相关的子项都显示在 "详细信息" 列表中。 例如，如果您的 <xref:System.Data.DataSet> 包含 Customers 表和相关订单表，则您可以将 Customers 表指定为主网格，将 Orders 表指定为详细信息网格。 从主网格中选择客户时，"订单" 表中与该客户关联的所有订单都将显示在 "详细信息" 网格中。

 下面的过程需要一个**Windows 应用程序**项目 **（文件** > **新**的 > **项目** > **视觉对象C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**）。

## <a name="to-create-a-master-details-list-in-the-designer"></a>在设计器中创建主-详细信息列表

1. 向窗体添加两个 <xref:System.Windows.Forms.DataGrid> 控件。 有关详细信息，请参阅[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。 在 Visual Studio 2005 中，默认情况下，<xref:System.Windows.Forms.DataGrid> 控件不在**工具箱**中。 有关详细信息，请参阅[如何：向工具箱添加项](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))。

    > [!NOTE]
    > 以下步骤不适用于 Visual Studio 2005，后者使用 "**数据源**" 窗口进行设计时数据绑定。 有关详细信息，请参阅[在 Visual Studio 中将控件绑定到数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)和[如何：在 Windows 窗体应用程序中显示相关数据](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))。

2. 将两个或多个表从**服务器资源管理器**拖动到窗体。

3. 从 "**数据**" 菜单中，选择 "**生成数据集**"。

4. 使用 "XML 设计器" 设置表之间的关系。 有关详细信息，请参阅 MSDN 上的 "如何：在 XML 架构和数据集创建一对多关系"。

5. 通过从 "**文件**" 菜单中选择 "**全部保存**" 来保存关系。

6. 配置要指定主网格的 <xref:System.Windows.Forms.DataGrid> 控件，如下所示：

    1. 从 "<xref:System.Windows.Forms.DataGrid.DataSource%2A>" 属性的下拉列表中选择 "<xref:System.Data.DataSet>"。

    2. 从 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 属性的下拉列表中选择主表（例如 "Customers"）。

7. 配置要指定详细信息网格的 <xref:System.Windows.Forms.DataGrid> 控件，如下所示：

    1. 从 "<xref:System.Windows.Forms.DataGrid.DataSource%2A>" 属性的下拉列表中选择 "<xref:System.Data.DataSet>"。

    2. 从 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 属性的下拉列表中选择主表和详细信息表之间的关系（例如 "CustOrd"）。 若要查看关系，请在下拉列表中单击 "主表" 旁边的加号（ **+** ），展开该节点。

## <a name="see-also"></a>另请参阅

- [DataGrid 컨트롤](datagrid-control-windows-forms.md)
- [DataGrid 컨트롤 개요](datagrid-control-overview-windows-forms.md)
- [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
