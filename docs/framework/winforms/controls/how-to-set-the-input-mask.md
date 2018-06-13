---
title: 如何：设置输入掩码
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 6f554c239e3444db5f6ac84f7994108ac70df0a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537036"
---
# <a name="how-to-set-the-input-mask"></a>如何：设置输入掩码
掩码的文本框控件为增强的文本框控件支持的声明性语法，用于接受或拒绝用户输入。 通过设置掩码属性，可以指定允许用户输入，而无需编写任何自定义验证逻辑应用程序中。 有关详细信息，请参阅备注部分的<xref:System.Windows.Forms.MaskedTextBox>类。  
  
## <a name="setting-the-mask-property-manually"></a>手动设置掩码属性  
 如果你熟悉掩码属性支持的字符，则可以手动输入它。 掩码属性支持的字符的摘要，请参阅备注部分的<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>属性。  
  
#### <a name="to-set-the-mask-property-manually"></a>若要手动设置掩码属性  
  
1.  在**设计**视图中，选择<xref:System.Windows.Forms.MaskedTextBox>。  
  
2.  在**属性**窗口中，找到<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>属性。  
  
3.  键入所需的掩码。 例如，键入`###`。  
  
## <a name="using-the-input-mask-dialog-box"></a>使用输入的掩码对话框  
 输入掩码对话框中提供了一些预定义的输入的掩码。 你还可以更改预定义的掩码或手动输入自己的掩码。  
  
#### <a name="to-open-the-input-mask-dialog-box"></a>若要打开输入掩码对话框  
  
1.  在**设计**视图中，选择<xref:System.Windows.Forms.MaskedTextBox>。  
  
    1.  单击要打开的智能标记**MaskedTextBox 任务**面板。  
  
    2.  单击**设置掩码**。  
  
     \- 或 -  
  
    1.  在**属性**窗口中，选择<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>属性。  
  
    2.  单击属性值列中的省略号按钮。  
  
     **输入掩码**对话框随即出现。  
  
#### <a name="to-use-the-input-mask-dialog-box"></a>若要使用的输入掩码对话框  
  
1.  （可选）单击其中一个列表中预定义的掩码。  
  
2.  （可选）编辑中的预定义的掩码**掩码**框。  
  
3.  （可选）输入新掩码**掩码**框。 也就是说，不需要使用一个预定义的掩码。  
  
    > [!NOTE]
    >  预览框中显示的字符，则用户将看到在<xref:System.Windows.Forms.MaskedTextBox>。 这些字符都是以帮助用户正确输入数据的指南。  
  
4.  选中或清除**使用 ValidatingType**复选框。 **使用 ValidatingType**复选框指定是否数据类型用于验证数据输入用户。 有关更多信息，请参见 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 属性。  
  
5.  单击 **“确定”**。  
  
     在输入掩码**掩码**中的属性**属性**窗口。  
  
## <a name="see-also"></a>请参阅  
 [演练：使用 MaskedTextBox 控件](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)
