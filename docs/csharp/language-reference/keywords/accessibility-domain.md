---
title: 可访问域（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 127bacda4bf8363fccff3dd3ef6770ad50984cfb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-domain-c-reference"></a>可访问域（C# 参考）
成员的可访问域可指定成员可以引用哪些程序分区。 如果成员嵌套于其他类型中，则该成员的可访问域是由该成员的[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)和直接包含类型的可访问域这二者共同确定的。  
  
 顶级类型的可访问域至少是在其中进行声明的项目的程序文本。 也就是说，该域包含此项目的所有源文件。 嵌套类型的可访问域至少是在其中进行声明的类型的程序文本。 也就是说，域是类型的主题，其中包括所有嵌套类型。 嵌套类型的可访问域决不能超出包含类型的可访问域。 下例说明了这些概念。  
  
## <a name="example"></a>示例  
 此示例包含一个顶级类型 `T1` 和两个嵌套类 `M1` 和 `M2`。 这两个类包含的字段具有不同的已声明可访问性。 在 `Main` 方法中，每条语句后跟注释以指示每个成员的可访问域。 请注意，试图引用不可访问成员的语句将被注释掉。如果想要查看通过引用不可访问成员引起的编译器错误，请一次删除一条注释。  
  
 [!code-csharp[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [对使用可访问性级别的限制](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [公用](../../../csharp/language-reference/keywords/public.md)  
 [专用](../../../csharp/language-reference/keywords/private.md)  
 [受保护](../../../csharp/language-reference/keywords/protected.md)  
 [内部](../../../csharp/language-reference/keywords/internal.md)
