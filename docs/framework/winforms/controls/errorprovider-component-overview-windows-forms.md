---
title: ErrorProvider 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
ms.openlocfilehash: b66e97d97d0d8c2ea4e9bdba29f8ff35e486e1f6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745787"
---
# <a name="errorprovider-component-overview-windows-forms"></a>ErrorProvider 구성 요소 개요(Windows Forms)
Windows 窗体[ErrorProvider](errorprovider-component-windows-forms.md)组件用于验证窗体或控件上的用户输入。 它通常与验证窗体上的用户输入，或在数据集内显示错误一起使用。 错误提供程序是一种比在消息框中显示错误消息的更好的替代方法，因为一旦关闭消息框，错误消息就不再可见。 <xref:System.Windows.Forms.ErrorProvider> 组件在相关控件（如文本框）旁显示错误图标（![](./media/errorprovider-component-overview-windows-forms/vb-error-provider-icon.gif)）旁边的红色感叹号。当用户将鼠标指针放置在错误图标上时，将显示一个工具提示，其中显示错误消息字符串。  
  
## <a name="key-properties"></a>키 속성  
 <xref:System.Windows.Forms.ErrorProvider> 组件的键属性为 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>、<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>和 <xref:System.Windows.Forms.ErrorProvider.Icon%2A>。 当使用包含数据绑定控件的 <xref:System.Windows.Forms.ErrorProvider> 组件时，必须将 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 属性设置为适当的容器（通常是 Windows 窗体），以便组件在窗体上显示错误图标。 在设计器中添加组件时，<xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 属性设置为包含窗体;如果在代码中添加控件，则必须自行设置。  
  
 <xref:System.Windows.Forms.ErrorProvider.Icon%2A> 属性可以设置为自定义错误图标而不是默认值。 设置 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 属性后，<xref:System.Windows.Forms.ErrorProvider> 组件可以显示数据集的错误消息。 <xref:System.Windows.Forms.ErrorProvider> 组件的关键方法是 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> 方法，该方法指定错误消息字符串以及应显示错误图标的位置。  
  
> [!NOTE]
> <xref:System.Windows.Forms.ErrorProvider> 组件不为辅助功能客户端提供内置支持。 이 구성 요소를 사용 하는 경우 애플리케이션에 액세스할 수 있도록, 추가, 액세스할 수 있는 피드백 메커니즘을 제공 해야 합니다.  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ErrorProvider>
- [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 세트에 있는 오류 보기](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
- [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시](display-error-icons-for-form-validation-with-wf-errorprovider.md)
