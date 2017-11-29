---
title: "remove（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: remove_CSharpKeyword
helpviewer_keywords: remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
caps.latest.revision: "8"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 66647dee0c4cc728ae5e19457a4a5ef0e7f72248
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="remove-c-reference"></a>remove（C# 参考）
`remove` 上下文关键字用于定义自定义事件访问器，当客户端代码订阅你的[事件](../../../csharp/language-reference/keywords/event.md)时将调用该访问器。 如果提供自定义 `remove` 访问器，还必须提供 [add](../../../csharp/language-reference/keywords/add.md) 访问器。  
  
## <a name="example"></a>示例  
 以下示例显示具有自定义 [add](../../../csharp/language-reference/keywords/add.md) 和 `remove` 访问器的事件。 有关完整示例，请参阅[如何：实现接口事件](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)。  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 通常不需要提供自己的自定义事件访问器。 大多数情况下，使用声明事件时由编译器自动生成的访问器就足够了。  
  
## <a name="see-also"></a>另请参阅  
 [事件](../../../csharp/programming-guide/events/index.md)
