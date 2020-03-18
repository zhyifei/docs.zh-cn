---
title: 可访问性域 - C# 参考
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 4a4319b03f3e0d7f9ec721e611b78c124a8a8ee5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713837"
---
# <a name="accessibility-domain-c-reference"></a>可访问域（C# 参考）
成员的可访问域可指定成员可以引用哪些程序分区。 如果成员嵌套于其他类型中，则该成员的可访问域是由该成员的[可访问性级别](./accessibility-levels.md)和直接包含类型的可访问域这二者共同确定的。  
  
 顶级类型的可访问域至少是在其中进行声明的项目的程序文本。 也就是说，该域包含此项目的所有源文件。 嵌套类型的可访问域至少是在其中进行声明的类型的程序文本。 也就是说，域是类型的主题，其中包括所有嵌套类型。 嵌套类型的可访问域决不能超出包含类型的可访问域。 下例说明了这些概念。  
  
## <a name="example"></a>示例  
 此示例包含一个顶级类型 `T1` 和两个嵌套类 `M1` 和 `M2`。 这两个类包含的字段具有不同的已声明可访问性。 在 `Main` 方法中，每条语句后跟注释以指示每个成员的可访问域。 请注意，试图引用不可访问成员的语句将被注释掉。如果想要查看通过引用不可访问成员引起的编译器错误，请一次删除一条注释。  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](./index.md)
- [访问修饰符](./access-modifiers.md)
- [可访问性级别](./accessibility-levels.md)
- [对使用可访问性级别的限制](./restrictions-on-using-accessibility-levels.md)
- [访问修饰符](../../programming-guide/classes-and-structs/access-modifiers.md)
- [public](./public.md)
- [专用](./private.md)
- [受保护](./protected.md)
- [internal](./internal.md)
