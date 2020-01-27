---
title: 使用设计器将一个按钮指定为 "取消" 按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 95d1139b6e339055f944ad0b0967a6d91283d49e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746050"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정
在任何 Windows 窗体上，都可以将 <xref:System.Windows.Forms.Button> 控件指定为 "取消" 按钮。 用户按 ESC 键时单击 "取消" 按钮，而不考虑窗体上的其他哪个控件具有焦点。 通常对此类按钮进行编程，使用户能够快速退出操作，而无需提交任何操作。

## <a name="to-designate-the-cancel-button"></a>指定 "取消" 按钮

1. 选择该按钮所在的窗体。

2. 在 "**属性**" 窗口中，将窗体的 <xref:System.Windows.Forms.Form.CancelButton%2A> 属性设置为 <xref:System.Windows.Forms.Button> 控件的名称。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Button 컨트롤 개요](button-control-overview-windows-forms.md)
- [Windows Forms Button 컨트롤 선택 방법](ways-to-select-a-windows-forms-button-control.md)
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
- [방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Button 컨트롤](button-control-windows-forms.md)
