---
title: "如何：将用户在 Web 控件中输入的数值转换为数字"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- parsing strings [.NET Framework], numeric strings
- converting numeric user input to number
- numbers [.NET Framework], converting numeric user input to number
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92e28e3b303a7523b9da69b7eb283e0261fc681c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a>如何：将用户在 Web 控件中输入的数值转换为数字
因为可以在世界任何地方显示网页，用户可以输入数字数据插入<xref:System.Web.UI.WebControls.TextBox>几乎无限数量的格式中的控件。 因此，它是用户的非常重要，以确定的区域设置和区域性，网页。 当分析用户输入时，你可以随后可应用定义的用户的区域设置和区域性的格式设置约定。  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a>若要从 Web 文本框控件的数字输入转换数字  
  
1.  确定返回的字符串数组<xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>填充属性。 如果不是，继续步骤 6。  
  
2.  如果通过返回的字符串数组<xref:System.Web.HttpRequest.UserLanguages%2A>填充属性，检索其第一个元素。 用户的默认值或首选的语言和区域，该值指示第一个元素。  
  
3.  实例化<xref:System.Globalization.CultureInfo>表示用户的对象的首选区域性，通过调用<xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>构造函数。  
  
4.  调用`TryParse`或`Parse`你想要转换的用户的数值类型的方法的输入转换为。 使用的重载`TryParse`或`Parse`方法替换`provider`参数，并将其传递下列操作之一：  
  
    -   <xref:System.Globalization.CultureInfo>步骤 3 中创建的对象。  
  
    -   <xref:System.Globalization.NumberFormatInfo>返回的对象<xref:System.Globalization.CultureInfo.NumberFormat%2A>属性<xref:System.Globalization.CultureInfo>步骤 3 中创建的对象。  
  
5.  如果转换失败，重复步骤 2 至 4 的每个剩余元素的字符串数组中返回<xref:System.Web.HttpRequest.UserLanguages%2A>属性。  
  
6.  如果转换仍失败，或通过返回的字符串数组<xref:System.Web.HttpRequest.UserLanguages%2A>属性为空，返回通过使用固定区域性，分析字符串<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>属性。  
  
## <a name="example"></a>示例  
 下面的示例是要求用户输入中的数值的 Web 窗体的完整的代码隐藏页<xref:System.Web.UI.WebControls.TextBox>控制并将其转换为数字。 然后，该数字是加倍，然后通过使用相同的格式设置规则作为原始输入显示。  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>中包含的区域性名称填充属性`Accept-Language`标头包含在 HTTP 请求中。 但是，并非所有浏览器包括`Accept-Language`其请求和用户中的标头还可以取消标头完全。 这使得重要有回退区域性，当用户输入内容分析。 通常，回退区域性是由固定区域性<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>。 用户还可以提供 Internet Explorer 并且了区域性名称它们输入在文本框中，这将创建区域性名称可能不是有效的可能性。 因此，务必要在实例化时使用异常处理<xref:System.Globalization.CultureInfo>对象。  
  
 当从 Internet Explorer 中，通过提交 HTTP 请求检索<xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>数组填充用户首选项的顺序。 数组中的第一个元素包含用户的主要的区域性区域的名称。 如果数组包含任何其他项，Internet Explorer 任意将其分配的质量说明符，它由分号分隔的区域性名称。 例如，FR-FR 区域性的条目可能采用的形式`fr-FR;q=0.7`。  
  
 该示例通过调用<xref:System.Globalization.CultureInfo.%23ctor%2A>构造函数使用其`useUserOverride`参数设置为`false`创建新<xref:System.Globalization.CultureInfo>对象。 这样可确保，如果区域性名称是默认区域性名称在服务器上，新<xref:System.Globalization.CultureInfo>由类构造函数创建对象包含区域性的默认设置，而不反映使用服务器的重写任何设置**区域和语言选项**应用程序。 从服务器上的任何重写设置的值不太可能存在于用户的系统上或才会反映在用户的输入。  
  
 你的代码可以调用`Parse`或`TryParse`的用户的输入的数值类型的方法将转换为。 一次分析操作可能需要重复的调用分析方法。 因此，`TryParse`方法是更好，因为它返回`false`如果分析操作失败。 与此相反，处理重复可能会引发的异常：`Parse`方法可以是 Web 应用程序中一种代价很高的做法。  
  
## <a name="compiling-the-code"></a>编译代码  
 若要编译代码，将其复制到[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]代码隐藏页中，以便它将替换现有的所有代码。 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web 页面应包含以下控件：  
  
-   A<xref:System.Web.UI.WebControls.Label>控件，这不在代码中引用。 设置其<xref:System.Web.UI.WebControls.TextBox.Text%2A>属性设置为"输入一个数字:"。  
  
-   名为 `NumericString` 的 <xref:System.Web.UI.WebControls.TextBox> 控件。  
  
-   名为 `OKButton` 的 <xref:System.Web.UI.WebControls.Button> 控件。 设置其<xref:System.Web.UI.WebControls.Button.Text%2A>属性设置为"确定"。  
  
 更改中的类名称`NumericUserInput`到由定义的类名称`Inherits`属性[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]页面的`Page`指令。 更改的名称`NumericInput`对象引用为通过定义的名称`id`属性[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]页面的`form`标记。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 若要防止用户脚本注入 HTML 流，可在服务器响应直接回送用户输入。 相反，它进行编码后应通过使用<xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType>方法。  
  
## <a name="see-also"></a>另请参阅  
 [执行格式设置操作](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [分析数值字符串](../../../docs/standard/base-types/parsing-numeric.md)
