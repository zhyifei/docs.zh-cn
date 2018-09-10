---
title: 分部类型（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 365d00d2c53d3efe1cd4330bdd3ec48740a49c53
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187043"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="5697f-102">分部类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5697f-102">partial type (C# Reference)</span></span>

<span data-ttu-id="5697f-103">通过分部类型可以定义要拆分到多个文件中的类、结构或接口。</span><span class="sxs-lookup"><span data-stu-id="5697f-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="5697f-104">在 File1.cs 中：</span><span class="sxs-lookup"><span data-stu-id="5697f-104">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="5697f-105">在 File2.cs 中，声明：</span><span class="sxs-lookup"><span data-stu-id="5697f-105">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="5697f-106">备注</span><span class="sxs-lookup"><span data-stu-id="5697f-106">Remarks</span></span>

<span data-ttu-id="5697f-107">在处理大型项目或自动生成的代码（如 [Windows 窗体设计器](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)提供的代码）时，在多个文件间拆分类、结构或接口类型可能会非常有用。</span><span class="sxs-lookup"><span data-stu-id="5697f-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="5697f-108">分部类型可以包含[分部方法](partial-method.md)。</span><span class="sxs-lookup"><span data-stu-id="5697f-108">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="5697f-109">有关详细信息，请参阅[分部类和方法](../../programming-guide/classes-and-structs/partial-classes-and-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="5697f-109">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5697f-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5697f-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5697f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5697f-111">See also</span></span>

- [<span data-ttu-id="5697f-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5697f-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5697f-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5697f-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5697f-114">修饰符</span><span class="sxs-lookup"><span data-stu-id="5697f-114">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="5697f-115">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="5697f-115">Introduction to Generics</span></span>](../../programming-guide/generics/introduction-to-generics.md)