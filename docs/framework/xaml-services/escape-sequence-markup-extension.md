---
title: "{} 转义序列的标记扩展"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
caps.latest.revision: 
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8419a1e89d5e94b9868b0fd1fb81540253efca5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="-escape-sequence--markup-extension"></a>{} 转义序列/标记扩展
为属性值提供 XAML 转义序列。 转义序列被解释为文本的属性中允许的后续值。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a>XAML 属性元素用法  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|*literalValue*|后面的转义序列的文本字符串。 此字符串通常包含一个打开或关闭的大括号 （{或}）。|  
  
## <a name="remarks"></a>备注  
 使用转义序列 （{}），以便左大括号 （{}） 可用作在 XAML 中的原义字符。  
  
 XAML 读取器通常使用左大括号 （{}） 来表示标记扩展的入口点; 但是，他们首先检查以确定它是否是右大括号 （}） 的下一个字符。 仅当两个大括号 （{}） 相邻时，它们被视为的转义序列。  
  
 如果遇到此转义序列，XAML 读取器应处理以字符串形式的字符串的其余部分。 但是，如果转义序列应用于类型转换器的成员，该字符串会被类型转换，以解释 XAML 编写器。  
  
 转义序列不是一个标记扩展，并不由类。 但是，它是 XAML 读取器 （包括自定义 XAML 读取器） 应遵循的约定。  
  
 引号 （"） 不能用作这种方式的转义序列。 如果你需要设置为非内容属性的属性值的引号，使用属性元素语法和将引号内的属性元素中，字符串形式或使用 XML 字符实体。 对于内容的属性，在引号可以是整个内容。  
  
 指定必须在 XAML 标记扩展可能出现的位置包括命名空间限定符的 XML 类型时，可以经常需要转义序列 （{}）。 这包括启动的 XAML 特性值，并在标记扩展中，紧跟着等号 （=）。 下面的示例演示了 XAML 特性值的开头处显示的 XML 命名空间的转义序列。  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a>请参阅  
 [XAML 的类型转换器和标记扩展](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [XML 字符实体和 XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
