---
title: "如何：使用指针复制字节数组（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 375cab76063e4c77515d6b05b42f2d97ff3efc44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a>如何：使用指针复制字节数组（C# 编程指南）
下面的示例使用指针将字节从一个数组复制到另一个数组。  
  
 此示例使用 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 关键字，使你可以在 `Copy` 方法中使用指针。 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) 语句用于声明指向源数组和目标数组的指针。 这会将源数组和目标数组的位置固定在内存中，以便它们不会被垃圾回收所移动。 当完成 `fixed` 块后，将取消固定数组的内存块。 因为此示例中的 `Copy` 方法使用 `unsafe` 关键字，所以必须使用 /unsafe 编译器选项对其进行编译。 若要在 Visual Studio 中设置该选项，请右键单击项目名称，然后单击“属性”。 在“生成”选项卡上，选择“允许不安全代码”。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [不安全代码和指针](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [/unsafe（C# 编译器选项）](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)  
 [垃圾回收](../../../standard/garbage-collection/index.md)
