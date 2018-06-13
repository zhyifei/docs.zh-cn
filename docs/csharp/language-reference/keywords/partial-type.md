---
title: 分部（类型）（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 4f57149dd18deb08aa11b72d0a6d5f71b3838bd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266684"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="1a00f-102">分部（类型）（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1a00f-102">partial (Type) (C# Reference)</span></span>
<span data-ttu-id="1a00f-103">通过分部类型可以定义要拆分到多个文件中的类、结构或接口。</span><span class="sxs-lookup"><span data-stu-id="1a00f-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>  
  
 <span data-ttu-id="1a00f-104">在 File1.cs 中：</span><span class="sxs-lookup"><span data-stu-id="1a00f-104">In File1.cs:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 <span data-ttu-id="1a00f-105">在 File2.cs 中，声明：</span><span class="sxs-lookup"><span data-stu-id="1a00f-105">In File2.cs the declaration:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="1a00f-106">备注</span><span class="sxs-lookup"><span data-stu-id="1a00f-106">Remarks</span></span>  
 <span data-ttu-id="1a00f-107">在处理大型项目或自动生成的代码（如 [Windows 窗体设计器](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)提供的代码）时，在多个文件间拆分类、结构或接口类型可能会非常有用。</span><span class="sxs-lookup"><span data-stu-id="1a00f-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="1a00f-108">分部类型可以包含[分部方法](../../../csharp/language-reference/keywords/partial-method.md)。</span><span class="sxs-lookup"><span data-stu-id="1a00f-108">A partial type may contain a [partial method](../../../csharp/language-reference/keywords/partial-method.md).</span></span> <span data-ttu-id="1a00f-109">有关详细信息，请参阅[分部类和方法](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="1a00f-109">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1a00f-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="1a00f-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1a00f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a00f-111">See Also</span></span>  
 [<span data-ttu-id="1a00f-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1a00f-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1a00f-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1a00f-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1a00f-114">修饰符</span><span class="sxs-lookup"><span data-stu-id="1a00f-114">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="1a00f-115">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="1a00f-115">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)
