---
title: "如何：在 C# 中定义常量"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ff12d0b6882289da9ed924f1c7de00edc5dc1e2e
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-define-constants-in-c"></a>如何：在 C# 中定义常量
常量是在编译时设置其值并且永远不能更改其值的字段。 使用常量可以为特殊值提供有意义的名称，而不是数字文本（“幻数”）。  
  
> [!NOTE]
>  在 C# 中，不能以 C 和 C++ 中通常采用的方式使用 [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 预处理器指令定义常量。  
  
 若要定义整型类型（`int`、`byte` 等）的常量值，请使用枚举类型。 有关详细信息，请参阅[枚举](../../../csharp/language-reference/keywords/enum.md)。  
  
 若要定义非整型常量，一种方法是将它们分组到一个名为 `Constants` 的静态类。 这要求对常量的所有引用都在其前面加上该类名，如下例所示。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 使用类名限定符有助于确保你和使用该常量的其他人了解它是常量并且不能修改。  
  
## <a name="see-also"></a>另请参阅  
 [类和结构](../../../csharp/programming-guide/classes-and-structs/index.md)
