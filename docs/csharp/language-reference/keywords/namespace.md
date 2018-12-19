---
title: namespace 关键字 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: b5c6b8081c188d5b184930222d54ad8f4b5d7a71
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242758"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="3fbee-102">命名空间（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3fbee-102">namespace (C# Reference)</span></span>

<span data-ttu-id="3fbee-103">`namespace` 关键字用于声明包含一组相关对象的作用域。</span><span class="sxs-lookup"><span data-stu-id="3fbee-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="3fbee-104">可以使用命名空间来组织代码元素并创建全局唯一类型。</span><span class="sxs-lookup"><span data-stu-id="3fbee-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="3fbee-105">备注</span><span class="sxs-lookup"><span data-stu-id="3fbee-105">Remarks</span></span>

<span data-ttu-id="3fbee-106">在命名空间中，可以声明零个或多个以下类型：</span><span class="sxs-lookup"><span data-stu-id="3fbee-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="3fbee-107">另一个命名空间</span><span class="sxs-lookup"><span data-stu-id="3fbee-107">another namespace</span></span>

- [<span data-ttu-id="3fbee-108">class</span><span class="sxs-lookup"><span data-stu-id="3fbee-108">class</span></span>](class.md)

- [<span data-ttu-id="3fbee-109">接口</span><span class="sxs-lookup"><span data-stu-id="3fbee-109">interface</span></span>](interface.md)

- [<span data-ttu-id="3fbee-110">struct</span><span class="sxs-lookup"><span data-stu-id="3fbee-110">struct</span></span>](struct.md)

- [<span data-ttu-id="3fbee-111">enum</span><span class="sxs-lookup"><span data-stu-id="3fbee-111">enum</span></span>](enum.md)

- [<span data-ttu-id="3fbee-112">delegate</span><span class="sxs-lookup"><span data-stu-id="3fbee-112">delegate</span></span>](delegate.md)

<span data-ttu-id="3fbee-113">无论是否在 C# 源文件中显式声明命名空间，编译器都会添加一个默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="3fbee-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="3fbee-114">此未命名的命名空间（有时被称为全局命名空间）存在于每个文件中。</span><span class="sxs-lookup"><span data-stu-id="3fbee-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="3fbee-115">全局命名空间中的任何标识符都可用于已命名的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3fbee-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="3fbee-116">命名空间隐式具有公共访问权限，这是不可修改的。</span><span class="sxs-lookup"><span data-stu-id="3fbee-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="3fbee-117">有关可以分配给命名空间中元素的访问修饰符的讨论，请参阅[访问修饰符](access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="3fbee-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="3fbee-118">可以在两个或多个声明中定义一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="3fbee-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="3fbee-119">例如，以下示例将两个类定义为 `MyCompany` 命名空间的一部分：</span><span class="sxs-lookup"><span data-stu-id="3fbee-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="3fbee-120">示例</span><span class="sxs-lookup"><span data-stu-id="3fbee-120">Example</span></span>

<span data-ttu-id="3fbee-121">以下示例显示如何在嵌套命名空间中调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="3fbee-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a><span data-ttu-id="3fbee-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="3fbee-122">Related resources</span></span>

<span data-ttu-id="3fbee-123">有关使用命名空间的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="3fbee-123">For more information about using namespaces, see the following topics:</span></span>

- [<span data-ttu-id="3fbee-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="3fbee-124">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

- [<span data-ttu-id="3fbee-125">使用命名空间</span><span class="sxs-lookup"><span data-stu-id="3fbee-125">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

- [<span data-ttu-id="3fbee-126">如何：使用全局命名空间别名</span><span class="sxs-lookup"><span data-stu-id="3fbee-126">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="3fbee-127">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3fbee-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3fbee-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fbee-128">See also</span></span>

- [<span data-ttu-id="3fbee-129">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3fbee-129">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="3fbee-130">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3fbee-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3fbee-131">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="3fbee-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3fbee-132">命名空间关键字</span><span class="sxs-lookup"><span data-stu-id="3fbee-132">Namespace Keywords</span></span>](namespace-keywords.md)
- [<span data-ttu-id="3fbee-133">using</span><span class="sxs-lookup"><span data-stu-id="3fbee-133">using</span></span>](using.md)