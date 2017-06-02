---
title: "对可以为 null 的类型执行装箱（C# 编程指南）| Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: 12
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
ms.openlocfilehash: e4ff2e8a31ca5a59494f80597460e90107e78c8a
ms.contentlocale: zh-cn
ms.lasthandoff: 03/24/2017

---
# <a name="boxing-nullable-types-c-programming-guide"></a>装箱可以为 null 的类型（C# 编程指南）
基于可以为 null 的类型的对象仅在其不为 null 时才可装箱。 如果 <xref:System.Nullable%601.HasValue%2A> 为 `false`，则对象引用将分配给 `null` 而不是进行装箱。 例如：  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 如果对象为非 null -- 如果 <xref:System.Nullable%601.HasValue%2A> 为 `true`，则将发生装箱，但仅装箱可以为 null 的对象所基于的基础类型。 装箱某个可以为 null 的非 null 值类型将装箱该值类型本身，而不是装箱用于包装该值类型的 <xref:System.Nullable%601?displayProperty=fullName>。 例如：  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 两个已装箱的对象与通过装箱不可为 null 的类型所创建的对象相同。 并且，与不可以为 null 的装箱类型一样，可将其取消装箱为可为 null 的类型，如以下示例所示：  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a>备注  
 可以为 null 的类型在装箱时的行为可提供两大好处：  
  
1.  可以为 null 的对象和其装箱的对应项可进行 null 测试：  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  装箱的可以为 null 的类型完全支持基础类型的功能：  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)   
 [可以为 null 的类型](../../../csharp/programming-guide/nullable-types/index.md)   
 [如何：标识可以为 null 的类型](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
