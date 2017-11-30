---
title: ".NET 中分析其他字符串"
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
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edd48993f50ec8b91ba7941a682d7de9f22aa12e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-other-strings-in-net"></a>.NET 中分析其他字符串
除了数值和<xref:System.DateTime>字符串，还可以分析表示类型的字符串<xref:System.Char>， <xref:System.Boolean>，和<xref:System.Enum>数据类型。  
  
## <a name="char"></a>Char  
 与 **Char** 数据类型关联的静态分析方法 可用于将包含单个字符的字符串转换为其 Unicode 值。 下面的代码示例将字符串分析为 Unicode 字符。  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a>Boolean  
 **布尔**数据类型包含**分析**可用于将转换到实际表示一个布尔值的字符串的方法**布尔**类型。 此方法不区分大小写，可以成功分析包含“True”或“False”的字符串。 **分析**与关联方法**布尔**类型还可以分析包围空格的字符串。 如果传递的其他任何字符串，<xref:System.FormatException>引发。  
  
 下面的代码示例使用**分析**方法将字符串转换为一个布尔值。  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a>枚举  
 可以使用静态 **Parse** 方法将枚举类型初始化为字符串的值。 此方法接受所分析的枚举类型、 字符串进行分析、 和可选的布尔型标志，该值指示分析区分大小写。 所分析的字符串可以包含用逗号分隔的多个值，这些值前面或后面可以是一个或多个空白（也称为空格）。 当字符串包含多个值时，返回的对象的值是所有指定值通过按位 OR 运算组合的值。  
  
 下面的示例使用**分析**方法将字符串表示形式转换为一个枚举值。 <xref:System.DayOfWeek>枚举初始化为**星期四**从字符串。  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a>另请参阅  
 [分析字符串](../../../docs/standard/base-types/parsing-strings.md)  
 [格式设置类型](../../../docs/standard/base-types/formatting-types.md)  
 [.NET 中的类型转换](../../../docs/standard/base-types/type-conversion.md)
