---
title: "如何：定义和使用自定义数值格式提供程序"
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
- custom numeric format strings
- numbers [.NET Framework], custom numeric format strings
- displaying date and time data
- format providers [.NET Framework]
- custom format strings
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e44a909eb92f0d9dfa21980a918a2d370dcf427
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>如何：定义和使用自定义数值格式提供程序
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]可让你全面控制的字符串表示形式的数字值。 它支持用于自定义数值格式的以下功能：  
  
-   标准数字格式字符串，提供一组预定义格式以用于将数字转换为其字符串表示形式。 可以使用任何数字格式设置方法，如<xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>，具有`format`参数。 有关详细信息，请参阅[标准数字格式字符串](../../../docs/standard/base-types/standard-numeric-format-strings.md)。  
  
-   自定义数字格式字符串，提供一组可以进行组合以定义自定义数字格式说明符的符号。 它们还可与任何数字格式设置方法，如<xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>，具有`format`参数。 有关详细信息，请参阅[自定义数字格式字符串](../../../docs/standard/base-types/custom-numeric-format-strings.md)。  
  
-   自定义<xref:System.Globalization.CultureInfo>或<xref:System.Globalization.NumberFormatInfo>对象，用于定义符号和格式显示数字值的字符串表示形式之间实现中使用的模式。 可以使用任何数字格式设置方法，如<xref:System.Int32.ToString%2A>，具有`provider`参数。 通常情况下，`provider`参数用于指定区域性特定格式设置。  
  
 在某些情况下（例如当应用程序必须显示格式化帐号、标识号或邮政编码），这三种方法都不合适。 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]还允许你定义的格式化对象，既不是<xref:System.Globalization.CultureInfo>也不是<xref:System.Globalization.NumberFormatInfo>对象确定如何设置格式的数字值。 本主题提供用于实现这类对象的分步说明，并提供对电话号码设置格式的示例。  
  
### <a name="to-define-a-custom-format-provider"></a>定义自定义格式提供程序  
  
1.  定义一个类以实现<xref:System.IFormatProvider>和<xref:System.ICustomFormatter>接口。  
  
2.  实现 <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> 方法。 <xref:System.IFormatProvider.GetFormat%2A>是一个回调方法的格式设置方法 (如<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>方法) 调用以检索实际负责执行自定义格式设置的对象。 典型实现<xref:System.IFormatProvider.GetFormat%2A>执行下列任务：  
  
    1.  确定是否<xref:System.Type>对象作为一种方法传递参数表示<xref:System.ICustomFormatter>接口。  
  
    2.  如果该参数的确表示<xref:System.ICustomFormatter>接口，<xref:System.IFormatProvider.GetFormat%2A>返回实现的对象<xref:System.ICustomFormatter>负责提供自定义格式设置的接口。 通常，自定义格式设置对象返回其自身。  
  
    3.  如果参数不表示<xref:System.ICustomFormatter>接口，<xref:System.IFormatProvider.GetFormat%2A>返回`null`。  
  
3.  实现 <xref:System.ICustomFormatter.Format%2A> 方法。 调用此方法<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>方法和负责返回数字的字符串表示。 实现方法通常涉及以下步骤：  
  
    1.  （可选），请确保该方法以合法方式用于提供格式设置服务通过检查`provider`参数。 有关实现的对象设置格式<xref:System.IFormatProvider>和<xref:System.ICustomFormatter>，这涉及到测试`provider`与当前的格式设置对象的相等性的参数。  
  
    2.  确定格式设置对象是否应支持自定义格式说明符。 （例如，格式说明符“N”可能指示应以 NANP 格式输出美国电话号码，而“I”可能指示以 ITU-T 建议 E.123 格式进行输出。）如果使用格式说明符，则方法应处理特定格式说明符。 传递到方法中`format`参数。 如果没有说明符存在的值`format`参数是<xref:System.String.Empty?displayProperty=nameWithType>。  
  
    3.  检索的数字值传递给该方法为`arg`参数。 执行将它转换为其字符串表示形式所需的任何操作。  
  
    4.  返回的字符串表示形式`arg`参数。  
  
### <a name="to-use-a-custom-numeric-formatting-object"></a>使用自定义数字格式设置对象  
  
1.  创建自定义格式设置类的新实例。  
  
2.  调用<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>格式设置方法，将其传递的自定义格式设置的对象的格式设置说明符 (或<xref:System.String.Empty?displayProperty=nameWithType>，如果未使用的一种)，和要设置格式的数字值。  
  
## <a name="example"></a>示例  
 下面的示例定义了一个名为 `TelephoneFormatter` 的自定义数值格式提供程序，该提供程序将代表美国电话号码的数字转化为它的 NANP 或 E.123 格式。 该方法处理两个格式说明符“N”（输出 NANP 格式）和“I”（输出国际 E.123 格式）。  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 自定义数字格式提供程序可仅与<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>方法。 数字格式设置方法的其他重载 (如`ToString`) 具有类型的参数<xref:System.IFormatProvider>通过了所有<xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>实现<xref:System.Type>对象，表示<xref:System.Globalization.NumberFormatInfo>类型。 反过来，他们期望方法以返回<xref:System.Globalization.NumberFormatInfo>对象。 如果没有，则忽略自定义数字格式提供程序，与<xref:System.Globalization.NumberFormatInfo>对象在该处使用当前区域性的。 在示例中，`TelephoneFormatter.GetFormat`方法处理它可能不当而导致传递给格式设置方法，通过检查方法参数并返回数值的可能性`null`如果它不表示类型<xref:System.ICustomFormatter>。  
  
 如果自定义数字格式提供程序支持的格式说明符的一组，请确保你提供一个默认行为，如果在中使用的格式项中不提供任何格式说明符，则<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>方法调用。 在示例中，“N”是默认格式说明符。 这使数字可以通过提供显式格式说明符来转换为格式化电话号码。 下面的示例演示了此类方法调用。  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 但是它还允许在不存在格式说明符时进行转换。 下面的示例演示了此类方法调用。  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 如果定义没有默认的格式说明符，则你实现<xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType>方法应包括如下所示的代码，因此该.NET 可以提供格式设置代码不支持。  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 在此示例中，该方法用于实现<xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType>旨在作为回调方法以<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>方法。 因此，它会检查`formatProvider`参数，以确定其是否包含对当前的引用`TelephoneFormatter`对象。 但是，也可以直接从代码调用该方法。 在这种情况下，你可以使用`formatProvider`参数来提供<xref:System.Globalization.CultureInfo>或<xref:System.Globalization.NumberFormatInfo>提供区域性特定格式设置信息的对象。  
  
## <a name="compiling-the-code"></a>编译代码  
 在命令行上使用 csc.exe 或 vb.exe 代码编译。 若要编译中的代码[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，将其放入控制台应用程序项目模板。  
  
## <a name="see-also"></a>另请参阅  
 [执行格式设置操作](../../../docs/standard/base-types/performing-formatting-operations.md)
