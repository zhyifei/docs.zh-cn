---
title: 选择 Windows 窗体 Button 控件的方法
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 39696be1286efa68fa70b698ba9623911c90e352
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536323"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>选择 Windows 窗体 Button 控件的方法
Windows 窗体按钮可以选择通过以下方式：  
  
-   使用鼠标单击的按钮。  
  
-   调用该按钮的<xref:System.Windows.Forms.Control.Click>在代码中的事件。  
  
-   将焦点移到按钮，通过按 TAB 键，并按空格键或 enter 键，然后选择该按钮。  
  
-   按该按钮的访问密钥 （ALT + 带下划线的字母）。 有关访问密钥的详细信息，请参阅[如何： 为 Windows 窗体控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)。  
  
-   如果按钮是窗体的"接受"按钮，并按 enter 键选择此按钮时，即使另一个控件具有焦点，但该控件可以是另一个按钮、 多行文本框中或捕获 enter 键的自定义控件。  
  
-   如果按钮是窗体的"取消"按钮，按 esc 键选择此按钮时，即使另一个控件具有焦点。  
  
-   调用<xref:System.Windows.Forms.Button.PerformClick%2A>方法以编程方式选择按钮。  
  
## <a name="see-also"></a>请参阅  
 [Button 控件概述](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [如何：响应 Windows 窗体 Button 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Button 控件](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
