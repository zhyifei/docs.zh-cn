---
title: 如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: cc352f15fb1e8b531cd0f9b298b2db4ce649d3cf
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039638"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮
在任何 Windows 窗体上, 都可以<xref:System.Windows.Forms.Button>将控件指定为 "取消" 按钮。 用户按 ESC 键时单击 "取消" 按钮, 而不考虑窗体上的其他哪个控件具有焦点。 通常对此类按钮进行编程, 使用户能够快速退出操作, 而无需提交任何操作。

## <a name="to-designate-the-cancel-button"></a>指定 "取消" 按钮

1. 选择该按钮所在的窗体。

2. 在 "**属性**" 窗口中, 将窗<xref:System.Windows.Forms.Form.CancelButton%2A>体的属性<xref:System.Windows.Forms.Button>设置为控件的名称。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Button 控件概述](button-control-overview-windows-forms.md)
- [如何选择 Windows 窗体 Button 控件](ways-to-select-a-windows-forms-button-control.md)
- [如何：响应 Windows 窗体按钮单击](how-to-respond-to-windows-forms-button-clicks.md)
- [如何：使用设计器将 Windows 窗体按钮指定为 "接受" 按钮](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Button 控件](button-control-windows-forms.md)
