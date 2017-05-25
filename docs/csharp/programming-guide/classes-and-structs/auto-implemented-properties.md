---
title: "自动实现的属性（C# 编程指南）| Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: db4871f8f9b1333f6dcfd21ac04a2efb5c5719cd
ms.contentlocale: zh-cn
ms.lasthandoff: 03/24/2017

---
# <a name="auto-implemented-properties-c-programming-guide"></a>自动实现的属性（C# 编程指南）
在 C# 3.0 及更高版本，当属性访问器中不需要任何其他逻辑时，自动实现的属性会使属性声明更加简洁。 它们还允许客户端代码创建对象。 当你声明以下示例中所示的属性时，编译器将创建仅可以通过该属性的 `get` 和 `set` 访问器访问的专用、匿名支持字段。  
  
## <a name="example"></a>示例  
 下列示例演示一个简单的类，它具有某些自动实现的属性：  
  
 [!code-cs[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]  
  
 在 C# 6 和更高版本中，你可以像字段一样初始化自动实现属性：  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 上一示例中所示的类是可变的。 创建客户端代码后可以用于更改对象中的值。 在包含重要行为（方法）以及数据的复杂类中，通常有必要具有公共属性。 但是，对于较小类或仅封装一组值（数据）且只有很少行为或没有行为的结构，则应该通过声明 set 访问器为[专用](../../../csharp/language-reference/keywords/private.md)（对使用者的不可变）或通过声明仅一个 get 访问器（除构造函数外都不可变），使对象不可变。  有关详细信息，请参阅[如何：使用自动实现的属性实现轻量类](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md)。  
  
 动实现的属性上允许使用特性，但很明显支持字段上不允许，因为不能从你的源代码访问它们。 如果必须使用属性的支持字段上的特性，只需创建一个常规属性。  
  
## <a name="see-also"></a>另请参阅  
 [属性](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [修饰符](../../../csharp/language-reference/keywords/modifiers.md)
