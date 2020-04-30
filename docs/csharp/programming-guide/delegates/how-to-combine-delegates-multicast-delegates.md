---
title: 如何合并委托（多播委托）- C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 7b5b9ba5c9bf70983fac9f869836b4c8c5449eca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705374"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a>如何合并委托（多播委托）（C# 编程指南）
此示例演示如何创建多播委托。 [委托](../../language-reference/builtin-types/reference-types.md)对象的一个有用之处在于可通过使用 `+` 运算符将多个对象分配到一个委托实例。 多播委托包含一个被分配的委托列表。当一个多播委托被调用时，它会依次调用列表中的委托。 仅可合并类型相同的委托。  
  
 `-` 运算符可用于从多播委托中删除组件委托。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.MulticastDelegate>
- [C# 编程指南](../index.md)
- [事件](../events/index.md)
