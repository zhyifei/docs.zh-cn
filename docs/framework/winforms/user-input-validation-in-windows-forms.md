---
title: 用户输入验证
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: eafbf54552566011fef9d2dbeb5e9f9fa3facabd
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646302"
---
# <a name="user-input-validation-in-windows-forms"></a>Windows 窗体中的用户输入验证
当用户在应用程序中输入数据时，您可能希望在应用程序使用数据之前验证数据是否有效。 您可以要求某些文本字段不是零长度，字段必须格式化为电话号码或其他类型的格式良好的数据，或者字符串不包含任何可能用于危害数据库安全性的不安全字符。 Windows 窗体提供了几种验证应用程序中输入的方法。  
  
## <a name="validation-with-the-maskedtextbox-control"></a>使用蒙版文本框控件进行验证  
 如果需要要求用户以定义良好的格式（如电话号码或部件号）输入数据，则可以使用<xref:System.Windows.Forms.MaskedTextBox>控件快速且使用最少的代码完成此任务。 *蒙版*是由掩蔽语言中的字符组成的字符串，用于指定可以在文本框中的任何给定位置输入哪些字符。 该控件向用户显示一组提示。 如果用户键入不正确的条目，例如，当用户在需要数字时键入字母，控件将自动拒绝输入。  
  
 所使用的掩蔽语言<xref:System.Windows.Forms.MaskedTextBox>非常灵活。 它允许您指定所需的字符、可选字符、字面字符（如连字符和括号、货币字符和日期分隔符）。 绑定到数据源时，该控件也工作正常。 数据<xref:System.Windows.Forms.Binding.Format>绑定上的事件可用于重格式化传入数据以符合掩码，该<xref:System.Windows.Forms.Binding.Parse>事件可用于重格式化传出数据以符合数据字段的规范。  
  
 有关详细信息，请参阅[蒙版文本框控件](./controls/maskedtextbox-control-windows-forms.md)。  
  
## <a name="event-driven-validation"></a>事件驱动验证  
 如果要对验证进行完全编程控制，或者需要执行复杂的验证检查，则应使用大多数 Windows 窗体控件中内置的验证事件。 接受自由格式用户输入的每个控件都有一个<xref:System.Windows.Forms.Control.Validating>事件，该事件将在控件需要数据验证时发生。 在<xref:System.Windows.Forms.Control.Validating>事件处理方法中，您可以通过多种方式验证用户输入。 例如，如果您有一个必须包含邮政编码的文本框，则可以通过以下方式执行验证：  
  
- 如果邮政编码必须属于特定的邮政编码组，则可以对输入执行字符串比较，以验证用户输入的数据。 例如，如果邮政编码必须位于集 {10001、10002、10003}中，则可以使用字符串比较来验证数据。  
  
- 如果邮政编码必须采用特定形式，则可以使用正则表达式来验证用户输入的数据。 例如，要验证窗体`#####`或`#####-####`，可以使用正则表达式`^(\d{5})(-\d{4})?$`。 要验证窗体`A#A #A#`，可以使用正则表达式`[A-Z]\d[A-Z] \d[A-Z]\d`。 有关正则表达式的详细信息，请参阅[.NET 框架正则表达式](../../standard/base-types/regular-expressions.md)和[正则表达式示例](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md)。  
  
- 如果邮政编码必须是有效的美国邮政编码，您可以调用邮政编码 Web 服务来验证用户输入的数据。  
  
 事件<xref:System.Windows.Forms.Control.Validating>提供类型的对象<xref:System.ComponentModel.CancelEventArgs>。 如果确定控件的数据无效，则可以通过将此对象的属性<xref:System.Windows.Forms.Control.Validating><xref:System.ComponentModel.CancelEventArgs.Cancel%2A>设置为`true`取消事件。 如果不设置属性，Windows<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>窗体将假定该控件的验证成功，并引发该<xref:System.Windows.Forms.Control.Validated>事件。  
  
 有关验证 中的电子邮件地址的代码示例，<xref:System.Windows.Controls.TextBox>请参阅<xref:System.Windows.Forms.Control.Validating>。  
  
### <a name="data-binding-and-event-driven-validation"></a>数据绑定和事件驱动验证  
 当您将控件绑定到数据源（如数据库表）时，验证非常有用。 通过使用验证，可以确保控件的数据满足数据源所需的格式，并且不包含任何可能不安全的特殊字符，如引号和斜杠。  
  
 使用数据绑定时，控件中的数据在执行<xref:System.Windows.Forms.Control.Validating>事件期间会与数据源同步。 如果取消该<xref:System.Windows.Forms.Control.Validating>事件，数据将不会与数据源同步。  
  
> [!IMPORTANT]
> 如果<xref:System.Windows.Forms.Control.Validating>具有在事件发生后进行的自定义验证，则不会影响数据绑定。 例如，如果<xref:System.Windows.Forms.Control.Validated>尝试取消数据绑定的事件有代码，则数据绑定仍将发生。 在这种情况下，要<xref:System.Windows.Forms.Control.Validated>在事件中执行验证，请将控件的**数据源更新模式**属性（**下（数据绑定）（**\\**高级）** 从**On验证**更改为**从不**，并将*控制*`.DataBindings["`*\<YOURFIELD>*`"].WriteValue()`添加到验证代码中。  
  
### <a name="implicit-and-explicit-validation"></a>隐式和显式验证  
 那么，控件的数据何时得到验证？ 这由您，开发人员决定。 您可以根据应用程序的需求使用隐式或显式验证。  
  
#### <a name="implicit-validation"></a>隐式验证  
 隐式验证方法在用户输入数据时验证数据。 通过在按下键时读取数据输入数据时验证数据，或者当用户将输入焦点从一个控件移开并移动到下一个控件时，更常见的验证数据。 当您希望向用户提供有关数据工作时的即时反馈时，此方法非常有用。  
  
 如果要对控件使用隐式验证，则必须将该控件的属性<xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>设置为<xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>或<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>。 如果取消该<xref:System.Windows.Forms.Control.Validating>事件，控件的行为将由分配给 的值决定<xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>。 如果分配<xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>，取消事件将导致<xref:System.Windows.Forms.Control.Validated>事件不会发生。 输入焦点将保留在当前控件上，直到用户将数据更改为有效输入。 如果分配<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>了<xref:System.Windows.Forms.Control.Validated>，则取消事件时不会发生事件，但焦点仍将更改为下一个控件。  
  
 分配给<xref:System.Windows.Forms.AutoValidate.Disable>属性<xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>可完全防止隐式验证。 要验证控件，必须使用显式验证。  
  
#### <a name="explicit-validation"></a>显式验证  
 显式验证方法一次验证数据。 您可以验证数据以响应用户操作，例如单击"保存"按钮或"下一步"链接。 发生用户操作时，可以通过以下方式之一触发显式验证：  
  
- 调用<xref:System.Windows.Forms.ContainerControl.Validate%2A>以验证最后一个控件失去焦点。  
  
- 调用<xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A>以验证窗体或容器控件中的所有子控件。  
  
- 调用自定义方法以手动验证控件中的数据。  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Windows 窗体控件的默认隐式验证行为  
 不同的 Windows 窗体控件对其<xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>属性具有不同的默认值。 下表显示了最常见的控件及其默认值。  
  
|控制|默认验证行为|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|未在视觉工作室中公开的属性|  
|<xref:System.Windows.Forms.ToolStripContainer>|未在视觉工作室中公开的属性|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>关闭窗体和覆盖验证  
 当控件由于它包含的数据无效而保持焦点时，不可能以通常的方式之一关闭父窗体：  
  
- 通过单击"**关闭**"按钮。  
  
- 通过在 **"系统**"菜单中选择 **"关闭**"。  
  
- 通过以编程<xref:System.Windows.Forms.Form.Close%2A>方式调用方法。  
  
 但是，在某些情况下，您可能希望让用户关闭窗体，而不管控件中的值是否有效。 您可以通过为窗体<xref:System.Windows.Forms.Form.FormClosing>的事件创建处理程序来覆盖验证并关闭仍包含无效数据的窗体。 在这种情况下，将<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>属性设置为`false`。 这将强制窗体关闭。 有关详细信息及示例，请参阅<xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>。  
  
> [!NOTE]
> 如果强制以这种方式关闭窗体，则窗体控件中尚未保存的任何数据都将丢失。 此外，模态窗体在关闭控件时不会验证它们的内容。 您仍可以使用控件验证将焦点锁定到控件，但不必担心与关闭窗体相关的行为。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>
- <xref:System.Windows.Forms.FormClosingEventArgs?displayProperty=nameWithType>
- [MaskedTextBox 控件](./controls/maskedtextbox-control-windows-forms.md)
- [正则表达式示例](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md)
