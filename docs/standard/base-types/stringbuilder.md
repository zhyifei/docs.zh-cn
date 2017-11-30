---
title: "在.NET 中使用 StringBuilder 类"
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
- cpp
helpviewer_keywords:
- Remove method
- strings [.NET Framework], capacities
- StringBuilder object
- Replace method
- AppendFormat method
- Append method
- Insert method
- strings [.NET Framework], StringBuilder object
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3a6c8f6dee9f2a1da6ed4a8219c1b4832464d9aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-stringbuilder-class-in-net"></a>在.NET 中使用 StringBuilder 类
<xref:System.String>对象是不可变。 每次使用中的方法之一<xref:System.String?displayProperty=nameWithType>类，你在内存中，这就需要为该新对象的新分配的空间创建新的字符串对象。 在你需要对字符串执行重复的修改的情况下，创建一个新关联的系统开销<xref:System.String>对象开销会很大。 <xref:System.Text.StringBuilder?displayProperty=nameWithType>类可用于当你想要修改字符串而不创建新对象。 例如，使用<xref:System.Text.StringBuilder>串联在一起在循环中的许多字符串时，类可以提升性能。  
  
## <a name="importing-the-systemtext-namespace"></a>导入 System.Text 命名空间  
 <xref:System.Text.StringBuilder>中找到该类<xref:System.Text>命名空间。  为了避免必须提供完全限定的类型名称在代码中，你可以导入<xref:System.Text>命名空间：  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a>实例化 StringBuilder 对象  
 你可以创建的新实例<xref:System.Text.StringBuilder>用一个重载构造函数方法，初始化变量，如下面的示例中所示的类。  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a>设置容量和长度  
 尽管<xref:System.Text.StringBuilder>是动态对象，您可以展开它所封装的字符串中的字符数可以指定的最大可保留的字符数的值。 此值称为该对象的容量，不应为字符串的长度相混淆，当前<xref:System.Text.StringBuilder>保存。 例如，你可能创建的新实例<xref:System.Text.StringBuilder>与字符串"Hello"，长度为 5，和你的类可能会指定该对象具有的最大容量为 25。 当修改<xref:System.Text.StringBuilder>，它不重新分配大小为自身直到达到容量。 当达到容量时，将自动分配新的空间且容量翻倍。 你可以指定的容量<xref:System.Text.StringBuilder>类使用重载构造函数之一。 下面的示例指定可以将 `MyStringBuilder` 对象增加到最多 25 个空间。  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 此外，你可以使用读/写<xref:System.Text.StringBuilder.Capacity%2A>属性来设置你的对象的最大长度。 下面的示例使用 **Capacity** 属性来定义对象的最大长度。  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 <xref:System.Text.StringBuilder.EnsureCapacity%2A>方法可以用于检查当前的容量**StringBuilder**。 如果容量大于传递的值，则不进行任何更改；但是，如果容量小于传递的值，则会更改当前的容量以使其与传递的值匹配。  
  
 <xref:System.Text.StringBuilder.Length%2A>属性还可以查看或设置。 如果将 **Length** 属性设置为大于 **Capacity** 属性的值，则自动将 **Capacity** 属性更改为与 **Length** 属性相同的值。 如果将 **Length** 属性设置为小于当前 **StringBuilder** 对象内的字符串长度的值，则会缩短该字符串。  
  
## <a name="modifying-the-stringbuilder-string"></a>修改 StringBuilder 字符串  
 下表列出了可用于修改 **StringBuilder** 内容的方法。  
  
|方法名称|使用|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|将信息追加到当前 **StringBuilder** 的末尾。|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|用带格式文本替换字符串中传递的格式说明符。|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|将字符串或对象插入到当前 **StringBuilder** 的指定索引中。|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|从当前 **StringBuilder** 中删除指定数量的字符。|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|替换指定索引处的指定字符。|  
  
### <a name="append"></a>追加  
 **追加**方法可以用于将文本或对象的字符串表示方法添加到表示由当前的字符串的末尾**StringBuilder**。 下面的示例将 **StringBuilder** 对象初始化为“Hello World”，然后将一些文本追加到该对象的末尾。 将根据需要自动分配空间。  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a>AppendFormat  
 <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>方法将文本添加到末尾<xref:System.Text.StringBuilder>对象。 它支持复合格式设置功能 (有关详细信息，请参阅[复合格式设置](../../../docs/standard/base-types/composite-formatting.md)) 通过调用<xref:System.IFormattable>实现或多个要设置格式的对象。 因此，它接受数字、日期和时间以及枚举值的标准格式字符串、数字以及日期和时间值的自定义格式字符串，以及为自定义类型定义的格式字符串。 （有关格式化的信息，请参阅[格式设置类型](../../../docs/standard/base-types/formatting-types.md)。）此方法可用于自定义变量的格式和追加到这些值<xref:System.Text.StringBuilder>。 下面的示例使用<xref:System.Text.StringBuilder.AppendFormat%2A>方法将一个整数值格式化为货币值的末尾<xref:System.Text.StringBuilder>对象。  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a>Insert  
 <xref:System.Text.StringBuilder.Insert%2A>方法将字符串或对象添加到指定位置在当前<xref:System.Text.StringBuilder>对象。 下面的示例使用此方法将一个单词插入到的第六个位置<xref:System.Text.StringBuilder>对象。  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a>删除  
 你可以使用**删除**方法来删除指定的数目的字符从当前<xref:System.Text.StringBuilder>对象，指定从零开始的索引位置开始。 下面的示例使用**删除**方法缩短<xref:System.Text.StringBuilder>对象。  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a>替换  
 **替换**方法可以用于替换中的字符<xref:System.Text.StringBuilder>对象与另一个指定字符。 下面的示例使用**替换**方法搜索<xref:System.Text.StringBuilder>对象的所有实例的感叹号字符 （！），并将其替换为问号字符 （？）。  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a>将 StringBuilder 对象转换为字符串  
 必须将转换<xref:System.Text.StringBuilder>对象传递给<xref:System.String>对象，然后可以将传递所表示的字符串<xref:System.Text.StringBuilder>对象的方法的具有<xref:System.String>参数或在用户界面中显示它。 通过调用来执行此转换<xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType>方法。 下面的示例调用数量的<xref:System.Text.StringBuilder>方法，然后调用<xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType>方法以显示的字符串。  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Text.StringBuilder?displayProperty=nameWithType>  
 [基本字符串操作](../../../docs/standard/base-types/basic-string-operations.md)  
 [格式设置类型](../../../docs/standard/base-types/formatting-types.md)
