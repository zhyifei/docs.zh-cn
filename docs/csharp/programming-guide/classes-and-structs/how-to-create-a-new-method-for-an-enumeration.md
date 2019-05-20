---
title: 如何：为枚举创建新方法 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 2ca388d19c0e4e1b098076caa5baa0a83cc0dd4c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65585877"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="fbf9b-102">如何：为枚举创建新方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fbf9b-102">How to: Create a New Method for an Enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="fbf9b-103">可使用扩展方法添加特定于某个特定枚举类型的功能。</span><span class="sxs-lookup"><span data-stu-id="fbf9b-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbf9b-104">示例</span><span class="sxs-lookup"><span data-stu-id="fbf9b-104">Example</span></span>  
 <span data-ttu-id="fbf9b-105">在下面的示例中，`Grades` 枚举表示学生可能在班里收到的字母等级分。</span><span class="sxs-lookup"><span data-stu-id="fbf9b-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="fbf9b-106">该示例将一个名为 `Passing` 的扩展方法添加到 `Grades` 类型中，以便该类型的每个实例现在都“知道”它是否表示合格的等级分。</span><span class="sxs-lookup"><span data-stu-id="fbf9b-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="fbf9b-107">请注意，`Extensions` 类还包含一个动态更新的静态变量，并且扩展方法的返回值反映了该变量的当前值。</span><span class="sxs-lookup"><span data-stu-id="fbf9b-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="fbf9b-108">这表明在幕后，将在定义扩展方法的静态类上直接调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="fbf9b-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf9b-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="fbf9b-109">See also</span></span>

- [<span data-ttu-id="fbf9b-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fbf9b-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fbf9b-111">扩展方法</span><span class="sxs-lookup"><span data-stu-id="fbf9b-111">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
