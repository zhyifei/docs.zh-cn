---
title: "如何：向 Web 用户显示本地化的日期和时间信息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- formatting [.NET Framework], dates
- parsing strings [.NET Framework], date and time strings
- localization [.NET Framework], date and time displays
- formatting [.NET Framework], localized data
- displaying date and time data
- localized date displays [.NET Framework]
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21493e0e0c9e42cf5efc42d86c8f126fbae9b392
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-localized-date-and-time-information-to-web-users"></a>如何：向 Web 用户显示本地化的日期和时间信息
因为可以在世界任何地方显示网页上，执行分析和格式化日期和时间值的操作不应依赖 （这通常是 Web 服务器的本地区域性的格式） 的默认格式与用户交互时。 相反，Web 窗体，该处理日期和时间字符串输入的用户应分析使用用户的首选的区域性的字符串。 同样，应符合用户的区域性的格式中的用户显示日期和时间数据。 本主题演示如何执行此操作。  
  
### <a name="to-parse-date-and-time-strings-input-by-the-user"></a>若要分析日期和时间字符串由用户输入  
  
1.  确定返回的字符串数组<xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>填充属性。 如果不是，继续步骤 6。  
  
2.  如果通过返回的字符串数组<xref:System.Web.HttpRequest.UserLanguages%2A>填充属性，检索其第一个元素。 用户的默认值或首选的语言和区域，该值指示第一个元素。  
  
3.  实例化<xref:System.Globalization.CultureInfo>表示用户的对象的首选区域性，通过调用<xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>构造函数。  
  
4.  调用`TryParse`或`Parse`方法<xref:System.DateTime>或<xref:System.DateTimeOffset>以尝试进行转换的类型。 使用的重载`TryParse`或`Parse`方法替换`provider`参数，并将其传递下列操作之一：  
  
    -   <xref:System.Globalization.CultureInfo>步骤 3 中创建的对象。  
  
    -   <xref:System.Globalization.DateTimeFormatInfo>返回的对象<xref:System.Globalization.CultureInfo.DateTimeFormat%2A>属性<xref:System.Globalization.CultureInfo>步骤 3 中创建的对象。  
  
5.  如果转换失败，重复步骤 2 至 4 的每个剩余元素的字符串数组中返回<xref:System.Web.HttpRequest.UserLanguages%2A>属性。  
  
6.  如果转换仍失败，或通过返回的字符串数组<xref:System.Web.HttpRequest.UserLanguages%2A>属性为空，返回通过使用固定区域性，分析字符串<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>属性。  
  
### <a name="to-parse-the-local-date-and-time-of-the-users-request"></a>若要分析的本地日期和时间的用户的请求  
  
1.  添加<xref:System.Web.UI.WebControls.HiddenField>到 Web 窗体控件。  
  
2.  创建一个 JavaScript 函数，处理`onClick`事件`Submit`按钮通过编写的当前日期和时间以及本地时区的偏移量从协调世界时 (UTC) 到<xref:System.Web.UI.WebControls.HiddenField.Value%2A>属性。 使用 （如分号） 分隔符来分隔字符串的两个组件。  
  
3.  使用 Web 窗体的<xref:System.Web.UI.Control.PreRender>事件以将该函数注入 HTML 通过将传递到脚本的文本输出流<xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>方法。  
  
4.  连接到的事件处理程序`Submit`按钮的`onClick`通过提供的 JavaScript 函数的名称的事件`OnClientClick`属性`Submit`按钮。  
  
5.  创建处理程序`Submit`按钮的<xref:System.Web.UI.WebControls.Button.Click>事件。  
  
6.  事件处理程序中，确定返回的字符串数组<xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>填充属性。 如果不是，继续步骤 14。  
  
7.  如果通过返回的字符串数组<xref:System.Web.HttpRequest.UserLanguages%2A>填充属性，检索其第一个元素。 用户的默认值或首选的语言和区域，该值指示第一个元素。  
  
8.  实例化<xref:System.Globalization.CultureInfo>表示用户的对象的首选区域性，通过调用<xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>构造函数。  
  
9. 将字符串分配给传递<xref:System.Web.UI.WebControls.HiddenField.Value%2A>属性<xref:System.String.Split%2A>方法来在单独的数组元素中存储的字符串表示形式的用户的本地日期和时间和的字符串表示形式的用户的本地时区偏移量。  
  
10. 调用<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>或<xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=nameWithType>方法将转换的日期和时间对用户的请求<xref:System.DateTime>值。 使用具有的方法的重载`provider`参数，并将其传递下列操作之一：  
  
    -   <xref:System.Globalization.CultureInfo>在步骤 8 中创建的对象。  
  
    -   <xref:System.Globalization.DateTimeFormatInfo>返回的对象<xref:System.Globalization.CultureInfo.DateTimeFormat%2A>属性<xref:System.Globalization.CultureInfo>在步骤 8 中创建的对象。  
  
11. 如果在步骤 10 中的分析操作失败，请转到步骤 13。 否则，调用<xref:System.UInt32.Parse%28System.String%29?displayProperty=nameWithType>方法将用户的时区偏移量的字符串表示转换为整数。  
  
12. 实例化<xref:System.DateTimeOffset>用户的本地时间表示通过调用<xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=nameWithType>构造函数。  
  
13. 如果在步骤 10 中的则转换失败，重复步骤 7 至 12 的每个剩余元素的字符串数组中返回<xref:System.Web.HttpRequest.UserLanguages%2A>属性。  
  
14. 如果转换仍失败，或通过返回的字符串数组<xref:System.Web.HttpRequest.UserLanguages%2A>属性为空，返回通过使用固定区域性，分析字符串<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>属性。 然后重复步骤 7 至 12。  
  
 结果是<xref:System.DateTimeOffset>表示网页中的用户的本地时间的对象。 然后，可以确定等效的 UTC 通过调用<xref:System.DateTimeOffset.ToUniversalTime%2A>方法。 您还可以确定等效的日期和时间在你的 Web 服务器上通过调用<xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>方法并传递的值<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>与要转换的时间的时区。  
  
## <a name="example"></a>示例  
 下面的示例包含 HTML 源和要求用户输入的日期和时间值的 ASP.NET Web 窗体的代码。 客户端脚本还有上的本地日期和时间的用户的请求和用户的时区偏移量的信息与写入 UTC 隐藏字段。 服务器返回一个网页，显示用户的输入中进行分析此信息。 它还显示的日期和时间的使用用户的本地时间、 时间、 UTC 服务器上的用户的请求。  
  
 [!code-aspx-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-aspx-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]
  
 客户端脚本调用 JavaScript`toLocaleString`方法。 这将生成遵循用户的区域设置，这是更有可能在服务器上已成功分析的格式设置约定的字符串。  
  
 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>中包含的区域性名称填充属性`Accept-Language`标头包含在 HTTP 请求中。 但是，并非所有浏览器包括`Accept-Language`其请求和用户中的标头还可以取消标头完全。 这使得重要有回退区域性，当用户输入内容分析。 通常，回退区域性是由固定区域性<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>。 用户还可以提供 Internet Explorer 并且了区域性名称它们输入在文本框中，这将创建区域性名称可能不是有效的可能性。 因此，务必要在实例化时使用异常处理<xref:System.Globalization.CultureInfo>对象。  
  
 当从 Internet Explorer 中，通过提交 HTTP 请求检索<xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>数组填充用户首选项的顺序。 数组中的第一个元素包含用户的主要的区域性区域的名称。 如果数组包含任何其他项，Internet Explorer 任意将其分配的质量说明符，它由分号分隔的区域性名称。 例如，FR-FR 区域性的条目可能采用的形式`fr-FR;q=0.7`。  
  
 该示例通过调用<xref:System.Globalization.CultureInfo.%23ctor%2A>构造函数使用其`useUserOverride`参数设置为`false`创建新<xref:System.Globalization.CultureInfo>对象。 这样可确保，如果区域性名称是默认区域性名称在服务器上，新<xref:System.Globalization.CultureInfo>由类构造函数创建对象包含区域性的默认设置，而不反映使用服务器的重写任何设置**区域和语言选项**应用程序。 从服务器上的任何重写设置的值不太可能存在于用户的系统上或才会反映在用户的输入。  
  
 因为此示例中要分析的日期和时间 （由用户，另一个存储到的隐藏字段的一个输入） 的两个字符串表示形式，它定义了可能<xref:System.Globalization.CultureInfo>提前可能需要的对象。 它创建的数组<xref:System.Globalization.CultureInfo>是一个大于返回的元素数的对象<xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>属性。 它然后实例化<xref:System.Globalization.CultureInfo>对象每个语言/区域字符串，并还实例化<xref:System.Globalization.CultureInfo>对象，表示<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>。  
  
 你的代码可以调用<xref:System.DateTime.Parse%2A>或<xref:System.DateTime.TryParse%2A>方法来转换用户的字符串表示形式的日期和时间为<xref:System.DateTime>值。 一次分析操作可能需要重复的调用分析方法。 因此，<xref:System.DateTime.TryParse%2A>方法是更好，因为它返回`false`如果分析操作失败。 与此相反，处理重复可能会引发的异常：<xref:System.DateTime.Parse%2A>方法可以是 Web 应用程序中一种代价很高的做法。  
  
## <a name="compiling-the-code"></a>编译代码  
 若要编译代码，创建[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]没有代码隐藏 Web 页。 然后，将该示例复制到 Web 页中，以便它将替换现有的所有代码。 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web 页面应包含以下控件：  
  
-   A<xref:System.Web.UI.WebControls.Label>控件，这不在代码中引用。 设置其<xref:System.Web.UI.WebControls.TextBox.Text%2A>属性设置为"输入一个数字:"。  
  
-   名为 `DateString` 的 <xref:System.Web.UI.WebControls.TextBox> 控件。  
  
-   名为 `OKButton` 的 <xref:System.Web.UI.WebControls.Button> 控件。 设置其<xref:System.Web.UI.WebControls.Button.Text%2A>属性设置为"确定"。  
  
-   名为 `DateInfo` 的 <xref:System.Web.UI.WebControls.HiddenField> 控件。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 若要防止用户脚本注入 HTML 流，可在服务器响应直接回送用户输入。 相反，它进行编码后应通过使用<xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType>方法。  
  
## <a name="see-also"></a>另请参阅  
 [执行格式设置操作](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
 [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)  
 [分析日期和时间字符串](../../../docs/standard/base-types/parsing-datetime.md)
