---
title: "Windows 窗体中的用户输入验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48a28db24731f9aa248bb149c9f19a57cf76bbf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="user-input-validation-in-windows-forms"></a>Windows 窗体中的用户输入验证
当用户输入到你的应用程序的数据时，你可能想要验证数据有效，然后再应用程序将使用它。 你可能需要某些文本字段不为零长度、 字段将转为电话号码或其他类型的数据格式正确，或字符串不包含任何不安全的字符，无法用于危及安全的数据库。 Windows 窗体提供了几种方法来验证你的应用程序中输入。  
  
## <a name="validation-with-the-maskedtextbox-control"></a>MaskedTextBox 控件的验证  
 如果你需要要求用户输入数据中明确定义的格式，如电话号码或的部件号，你可以通过完成此速度快、 最少的代码使用<xref:System.Windows.Forms.MaskedTextBox>控件。 A*掩码*是从一种屏蔽语言，用于指定可以在任何给定位置在文本框中输入的字符的字符组成的字符串。 控件向用户显示一组提示。 如果用户键入输入错误，例如，用户键入字母数字时所需，该控件将自动拒绝输入。  
  
 使用的屏蔽语言<xref:System.Windows.Forms.MaskedTextBox>非常灵活。 它允许你指定所需的字符、 可选的字符、 原义字符，例如连字符和括号，货币字符和日期分隔符。 控件也适用于很好地时绑定到数据源。 <xref:System.Windows.Forms.Binding.Format>的数据绑定事件可用于对传入的数据以符合掩码，重新设置格式和<xref:System.Windows.Forms.Binding.Parse>事件可用于重新设置格式要符合规范的数据字段的传出数据。  
  
 有关详细信息，请参阅[MaskedTextBox 控件](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)。  
  
## <a name="event-driven-validation"></a>事件驱动的验证  
 如果你想要以完全编程控制验证，或需要执行复杂的验证检查，则应使用内置于大多数 Windows 窗体控件的验证事件。 接受自由格式用户输入的每个控件具有<xref:System.Windows.Forms.Control.Validating>，该控件所需数据验证都会发生的事件。 在<xref:System.Windows.Forms.Control.Validating>事件处理方法，你可以验证用户输入以下几种方式。 例如，如果你有必须包含邮政编码的文本框中，你可以通过以下方式来执行验证：  
  
-   如果邮政编码必须属于一组特定的邮政编码，你可以对要验证用户输入的数据的输入执行字符串比较。 例如，如果邮政编码必须在 {10001、 10002，10003} 的集，然后可以使用字符串比较来验证数据。  
  
-   如果特定的形式必须为邮政代码可以使用正则表达式来验证用户输入的数据。 例如，若要验证的表单`#####`或`#####-####`，你可以使用正则表达式`^(\d{5})(-\d{4})?$`。 若要验证的表单`A#A #A#`，你可以使用正则表达式`[A-Z]\d[A-Z] \d[A-Z]\d`。 有关正则表达式的详细信息，请参阅[.NET Framework 正则表达式](../../../docs/standard/base-types/regular-expressions.md)和[正则表达式示例](../../../docs/standard/base-types/regular-expression-examples.md)。  
  
-   如果邮政编码必须是有效的美国邮政编码，则可以调用邮政编码 Web 服务以验证用户输入的数据。  
  
 <xref:System.Windows.Forms.Control.Validating>提供事件类型的对象<xref:System.ComponentModel.CancelEventArgs>。 如果你确定控件的数据无效，则可以取消<xref:System.Windows.Forms.Control.Validating>通过设置此对象的事件<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>属性`true`。 如果你未设置<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>属性，Windows 窗体将假定该验证成功对于该控件，并引发<xref:System.Windows.Forms.Control.Validated>事件。  
  
 有关验证电子邮件地址中的代码示例<xref:System.Windows.Controls.TextBox>，请参阅<xref:System.Windows.Forms.Control.Validating>。  
  
### <a name="data-binding-and-event-driven-validation"></a>数据绑定和事件驱动的验证  
 将控件绑定到数据源，如数据库表时，验证将非常有用。 通过使用验证，你可以确保控件的数据满足数据源所要求的格式和其不包含任何特殊字符如引号引起来，备份正斜杠可能不安全。  
  
 当使用数据绑定时，你的控件中的数据与同步数据源执行期间<xref:System.Windows.Forms.Control.Validating>事件。 如果你取消<xref:System.Windows.Forms.Control.Validating>事件，不会与数据源同步数据。  
  
> [!IMPORTANT]
>  如果你有之后发生的自定义验证<xref:System.Windows.Forms.Control.Validating>事件，它将不会影响的数据绑定。 例如，如果具有代码<xref:System.Windows.Forms.Control.Validated>尝试取消数据绑定的事件，仍将发生数据绑定。 在此情况下，若要执行中的验证<xref:System.Windows.Forms.Control.Validated>事件，更改控件的**数据源更新模式**属性 (**(Databindings) 下**\\**（高级）**) 从**OnValidation**到**从不**，并添加*控件*`.DataBindings["`*\<YOURFIELD >* `"].WriteValue()`到你的验证代码。  
  
### <a name="implicit-and-explicit-validation"></a>隐式和显式验证  
 因此何时控件的数据验证？ 这是由您决定，开发人员。 你可以使用隐式或显式验证，具体取决于你的应用程序的需求。  
  
#### <a name="implicit-validation"></a>隐式验证  
 在用户输入它时，隐式验证方法将验证数据。 你可以验证数据，因为通常每当用户将输入的焦点离开一个控件，并将移动到下一步，在通过读取的项，如您按下，控件或多个输入的数据。 当你想要将有关的数据的用户即时反馈，因为他们正在处理时，此方法非常有用。  
  
 如果你想要使用的控件的隐式验证，则必须设置该控件的<xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>属性`true`。 如果你取消<xref:System.Windows.Forms.Control.Validating>事件，该控件的行为将由何值你分配给<xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>。 如果分配<xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>，取消该事件将导致<xref:System.Windows.Forms.Control.Validated>事件不发生。 输入的焦点将保留在当前控件上，直到用户将数据更改为有效的输入。 如果分配<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>、<xref:System.Windows.Forms.Control.Validated>时取消该事件，但将仍会将焦点更改为下一个控件的事件将不会发生。  
  
 分配<xref:System.Windows.Forms.AutoValidate.Disable>到<xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>属性完全阻止隐式验证。 若要验证你的控件，你将需要使用显式验证。  
  
#### <a name="explicit-validation"></a>显式验证  
 显式验证方法一次验证数据。 你可以验证响应用户操作，例如单击保存按钮或下一步链接中的数据。 当用户执行任何操作发生时，你可以通过以下方式之一来触发显式验证：  
  
-   调用<xref:System.Windows.Forms.ContainerControl.Validate%2A>验证失去焦点的最后一个控件。  
  
-   调用<xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A>以验证窗体或容器控件中的所有子控件。  
  
-   调用自定义方法，以手动验证控件中的数据。  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>默认隐式验证行为适用于 Windows 窗体控件  
 不同的 Windows 窗体控件具有不同的默认值为其<xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>属性。 下表显示了最常见的控件以及各自的默认值。  
  
|控件|默认验证行为|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|不在 Visual Studio 中公开的属性|  
|<xref:System.Windows.Forms.ToolStripContainer>|不在 Visual Studio 中公开的属性|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>关闭窗体和重写验证  
 当控件保持焦点，因为它包含的数据无效时，不可能以常用方式之一关闭了父窗体：  
  
-   通过单击**关闭**按钮。  
  
-   通过选择**关闭**中**系统**菜单。  
  
-   通过调用<xref:System.Windows.Forms.Form.Close%2A>方法以编程方式。  
  
 但是，在某些情况下，你可能想要让用户关闭该窗体，而不考虑在控件中的值是否有效。 你可以重写验证并关闭仍包含无效的数据，通过创建的处理程序窗体的窗体<xref:System.Windows.Forms.Form.Closing>事件。 在事件中，设置<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>属性`false`。 这将强制关闭该窗体。 有关详细信息及示例，请参阅<xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>。  
  
> [!NOTE]
>  如果你强制执行这种方式关闭该窗体，则尚未保存的窗体的控件中的任何数据将丢失。 此外，模式的窗体被关闭时不会验证控件的内容。 您仍可以使用控件验证锁定焦点移到控件，但无需关心信息与关闭窗体关联的行为。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>  
 [MaskedTextBox 控件](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)  
 [正则表达式示例](../../../docs/standard/base-types/regular-expression-examples.md)
