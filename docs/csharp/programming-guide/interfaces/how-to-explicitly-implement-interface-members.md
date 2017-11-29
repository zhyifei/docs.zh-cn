---
title: "如何：显式实现接口成员（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e02ae26000057e4e7323a777a6a0e1ca6fd8871b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>如何：显式实现接口成员（C# 编程指南）
本示例声明一个[接口](../../../csharp/language-reference/keywords/interface.md) `IDimensions` 和一个类 `Box`，显式实现了接口成员 `getLength` 和 `getWidth`。 通过接口实例 `dimensions` 访问这些成员。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## <a name="robust-programming"></a>可靠编程  
  
-   请注意，注释掉了 `Main` 方法中以下行，因为它们将产生编译错误。 显式实现的接口成员不能从[类](../../../csharp/language-reference/keywords/class.md)实例访问：  
  
     [!code-csharp[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   另请注意 `Main` 方法中的以下行成功输出了框的尺寸，因为这些方法是从接口实例调用的：  
  
     [!code-csharp[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [类和结构](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [接口](../../../csharp/programming-guide/interfaces/index.md)  
 [如何：显式实现两个接口的成员](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
