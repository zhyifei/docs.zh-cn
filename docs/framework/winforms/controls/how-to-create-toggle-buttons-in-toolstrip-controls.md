---
title: 如何：在 ToolStrip 控件中创建切换按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 6a003b91cd4db5db2790a20db97dbaa4d8925e96
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972353"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>如何：在 ToolStrip 控件中创建切换按钮

当用户单击切换按钮时, 它会显示凹陷, 并保持凹陷外观, 直到用户再次单击此按钮。

## <a name="to-create-a-toggling-toolstripbutton"></a>创建切换 ToolStripButton

- 使用类似于下面的代码示例的代码。 此代码假定您的窗体包含<xref:System.Windows.Forms.ToolStrip>一个控件, 并且它<xref:System.Windows.Forms.ToolStrip.Items%2A>的集合包含<xref:System.Windows.Forms.ToolStripButton>一个`toolStripButton1`名为的。 它还假定您有一个名`toolStripButton1_CheckedChanged`为的事件处理程序。

    ```vb
    toolStripButton1.CheckOnClick = True
    toolStripButton1.CheckedChanged AddressOf _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

    ```csharp
    toolStripButton1.CheckOnClick = true;
    toolStripButton1.CheckedChanged += new _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ToolStripButton>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
