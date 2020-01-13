---
title: 如何为枚举创建新方法 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 0d8e562342239c8ac3c53e05086ede9c234d0b63
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705647"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="019d1-102">如何为枚举创建新方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="019d1-102">How to create a new method for an enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="019d1-103">可使用扩展方法添加特定于某个特定枚举类型的功能。</span><span class="sxs-lookup"><span data-stu-id="019d1-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="019d1-104">示例</span><span class="sxs-lookup"><span data-stu-id="019d1-104">Example</span></span>  
 <span data-ttu-id="019d1-105">在下面的示例中，`Grades` 枚举表示学生可能在班里收到的字母等级分。</span><span class="sxs-lookup"><span data-stu-id="019d1-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="019d1-106">该示例将一个名为 `Passing` 的扩展方法添加到 `Grades` 类型中，以便该类型的每个实例现在都“知道”它是否表示合格的等级分。</span><span class="sxs-lookup"><span data-stu-id="019d1-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="019d1-107">请注意，`Extensions` 类还包含一个动态更新的静态变量，并且扩展方法的返回值反映了该变量的当前值。</span><span class="sxs-lookup"><span data-stu-id="019d1-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="019d1-108">这表明在幕后，将在定义扩展方法的静态类上直接调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="019d1-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="019d1-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="019d1-109">See also</span></span>

- [<span data-ttu-id="019d1-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="019d1-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="019d1-111">扩展方法</span><span class="sxs-lookup"><span data-stu-id="019d1-111">Extension Methods</span></span>](./extension-methods.md)
