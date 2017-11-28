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
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="9b687-102">如何：使用指针复制字节数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9b687-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>
<span data-ttu-id="9b687-103">下面的示例使用指针将字节从一个数组复制到另一个数组。</span><span class="sxs-lookup"><span data-stu-id="9b687-103">The following example uses pointers to copy bytes from one array to another.</span></span>  
  
 <span data-ttu-id="9b687-104">此示例使用 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 关键字，使你可以在 `Copy` 方法中使用指针。</span><span class="sxs-lookup"><span data-stu-id="9b687-104">This example uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="9b687-105">[fixed](../../../csharp/language-reference/keywords/fixed-statement.md) 语句用于声明指向源数组和目标数组的指针。</span><span class="sxs-lookup"><span data-stu-id="9b687-105">The [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="9b687-106">这会将源数组和目标数组的位置固定在内存中，以便它们不会被垃圾回收所移动。</span><span class="sxs-lookup"><span data-stu-id="9b687-106">This *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="9b687-107">当完成 `fixed` 块后，将取消固定数组的内存块。</span><span class="sxs-lookup"><span data-stu-id="9b687-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="9b687-108">因为此示例中的 `Copy` 方法使用 `unsafe` 关键字，所以必须使用 /unsafe 编译器选项对其进行编译。</span><span class="sxs-lookup"><span data-stu-id="9b687-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the **/unsafe** compiler option.</span></span> <span data-ttu-id="9b687-109">若要在 Visual Studio 中设置该选项，请右键单击项目名称，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="9b687-109">To set the option in Visual Studio, right-click the project name, and then click **Properties**.</span></span> <span data-ttu-id="9b687-110">在“生成”选项卡上，选择“允许不安全代码”。</span><span class="sxs-lookup"><span data-stu-id="9b687-110">On the **Build** tab, select **Allow unsafe code**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b687-111">示例</span><span class="sxs-lookup"><span data-stu-id="9b687-111">Example</span></span>  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9b687-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b687-112">See Also</span></span>  
 [<span data-ttu-id="9b687-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="9b687-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9b687-114">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="9b687-114">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="9b687-115">/unsafe（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="9b687-115">/unsafe (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)  
 [<span data-ttu-id="9b687-116">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="9b687-116">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
