---
title: 如何：编写复制构造函数（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: d6ecfc3659dcf533db0f4e7b67fdffd620a584fd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44182001"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>如何：编写复制构造函数（C# 编程指南）
C# 不会为对象提供复制构造函数，但你可以自己编写一个。  
  
## <a name="example"></a>示例  
 在下面的示例中，`Person`[类](../../../csharp/language-reference/keywords/class.md)定义一个复制构造函数，该函数使用 `Person` 的实例作为其参数。 该参数的属性值分配给 `Person` 的新实例的属性。 该代码包含一个备用复制构造函数，该函数发送要复制到该类的实例构造函数的实例的 `Name` 和 `Age` 属性。  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.ICloneable>  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [类和结构](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [构造函数](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [终结器](../../../csharp/programming-guide/classes-and-structs/destructors.md)
