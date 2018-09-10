---
title: 泛型委托（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: 7596ace0ea404cc345d73c0979fa7bd03a26b047
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857531"
---
# <a name="generic-delegates-c-programming-guide"></a>泛型委托（C# 编程指南）
[委托](../../../csharp/language-reference/keywords/delegate.md)可以定义它自己的类型参数。 引用泛型委托的代码可以指定类型参数以创建封闭式构造类型，就像实例化泛型类或调用泛型方法一样，如以下示例中所示：  
  
 [!code-csharp[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]  
  
 C# 2.0 版具有一种称为方法组转换的新功能，适用于具体委托类型和泛型委托类型，使你能够使用此简化语法编写上一行：  
  
 [!code-csharp[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]  
  
 在泛型类中定义的委托可以用类方法使用的相同方式来使用泛型类类型参数。  
  
 [!code-csharp[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]  
  
 引用委托的代码必须指定包含类的类型参数，如下所示：  
  
 [!code-csharp[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]  
  
 根据典型设计模式定义事件时，泛型委托特别有用，因为发件人参数可以为强类型，无需在它和 <xref:System.Object> 之间强制转换。  
  
 [!code-csharp[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Collections.Generic>  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [泛型介绍](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
- [泛型方法](../../../csharp/programming-guide/generics/generic-methods.md)  
- [泛型类](../../../csharp/programming-guide/generics/generic-classes.md)  
- [泛型接口](../../../csharp/programming-guide/generics/generic-interfaces.md)  
- [委托](../../../csharp/programming-guide/delegates/index.md)  
- [泛型](~/docs/standard/generics/index.md)
