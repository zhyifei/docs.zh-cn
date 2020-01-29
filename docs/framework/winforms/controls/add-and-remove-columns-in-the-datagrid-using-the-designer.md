---
title: 使用设计器在 DataGridView 控件中添加和删除列
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 717a0074f0750352a23b90a9b6e5eab1dc6c925a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732347"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거
Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件必须包含列才能显示数据。 如果你计划手动填充控件，则必须自行添加列。 或者，您可以将控件绑定到数据源，该数据源会自动生成并填充列。 如果数据源包含的列多于要显示的列数，则可以删除不需要的列。

 以下过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。 有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

## <a name="to-add-a-column-using-the-designer"></a>使用设计器添加列

1. 单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")），然后选择 "**添加列**"。

2. 在 "**添加列**" 对话框中，选择 "数据**绑定列**" 选项，然后从数据源中选择一个列，或选择 "**未绑定列**" 选项，然后使用提供的字段定义列。

3. 单击 "**添加**" 按钮添加列，如果现有列尚未填充控件显示区域，则会使其显示在设计器中。

    > [!NOTE]
    > 您可以在 "**编辑列**" 对话框中修改列属性，该对话框可从控件的智能标记访问。

## <a name="to-remove-a-column-using-the-designer"></a>使用设计器删除列

1. 从控件的智能标记中，选择 "**编辑列**"。

2. 从 "**选定的列**" 列表中选择一列。

3. 单击 "**删除**" 按钮可删除该列，使其从设计器中消失。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)
