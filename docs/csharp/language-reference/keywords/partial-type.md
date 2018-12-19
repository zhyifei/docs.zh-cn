---
title: 分部类型 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: ed3e18c5981fa52dc2c6ef09bfb666cfa705fede
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239561"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="b2f07-102">分部类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b2f07-102">partial type (C# Reference)</span></span>

<span data-ttu-id="b2f07-103">通过分部类型可以定义要拆分到多个文件中的类、结构或接口。</span><span class="sxs-lookup"><span data-stu-id="b2f07-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>

<span data-ttu-id="b2f07-104">在 File1.cs 中：</span><span class="sxs-lookup"><span data-stu-id="b2f07-104">In *File1.cs*:</span></span>

[!code-csharp[csrefKeywordsContextual#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#3)]  

<span data-ttu-id="b2f07-105">在 File2.cs 中，声明：</span><span class="sxs-lookup"><span data-stu-id="b2f07-105">In *File2.cs* the declaration:</span></span>

[!code-csharp[csrefKeywordsContextual#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#4)]  

## <a name="remarks"></a><span data-ttu-id="b2f07-106">备注</span><span class="sxs-lookup"><span data-stu-id="b2f07-106">Remarks</span></span>

<span data-ttu-id="b2f07-107">在处理大型项目或自动生成的代码（如 [Windows 窗体设计器](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)提供的代码）时，在多个文件间拆分类、结构或接口类型可能会非常有用。</span><span class="sxs-lookup"><span data-stu-id="b2f07-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="b2f07-108">分部类型可以包含[分部方法](partial-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b2f07-108">A partial type may contain a [partial method](partial-method.md).</span></span> <span data-ttu-id="b2f07-109">有关详细信息，请参阅[分部类和方法](../../programming-guide/classes-and-structs/partial-classes-and-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="b2f07-109">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b2f07-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b2f07-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b2f07-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2f07-111">See also</span></span>

- [<span data-ttu-id="b2f07-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b2f07-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b2f07-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b2f07-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b2f07-114">修饰符</span><span class="sxs-lookup"><span data-stu-id="b2f07-114">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="b2f07-115">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="b2f07-115">Introduction to Generics</span></span>](../../programming-guide/generics/introduction-to-generics.md)