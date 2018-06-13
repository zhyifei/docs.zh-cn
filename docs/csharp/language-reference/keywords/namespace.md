---
title: 命名空间（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: 343cce85dd235532fbe3fc90af0a785f48518db7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276014"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="8e2ff-102">命名空间（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8e2ff-102">namespace (C# Reference)</span></span>
<span data-ttu-id="8e2ff-103">`namespace` 关键字用于声明包含一组相关对象的作用域。</span><span class="sxs-lookup"><span data-stu-id="8e2ff-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="8e2ff-104">可以使用命名空间来组织代码元素并创建全局唯一类型。</span><span class="sxs-lookup"><span data-stu-id="8e2ff-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="8e2ff-105">备注</span><span class="sxs-lookup"><span data-stu-id="8e2ff-105">Remarks</span></span>  
 <span data-ttu-id="8e2ff-106">在命名空间中，可以声明一个或多个以下类型：</span><span class="sxs-lookup"><span data-stu-id="8e2ff-106">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="8e2ff-107">另一个命名空间</span><span class="sxs-lookup"><span data-stu-id="8e2ff-107">another namespace</span></span>  
  
-   [<span data-ttu-id="8e2ff-108">class</span><span class="sxs-lookup"><span data-stu-id="8e2ff-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="8e2ff-109">接口</span><span class="sxs-lookup"><span data-stu-id="8e2ff-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="8e2ff-110">struct</span><span class="sxs-lookup"><span data-stu-id="8e2ff-110">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="8e2ff-111">enum</span><span class="sxs-lookup"><span data-stu-id="8e2ff-111">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="8e2ff-112">delegate</span><span class="sxs-lookup"><span data-stu-id="8e2ff-112">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="8e2ff-113">无论是否在 C# 源文件中显式声明命名空间，编译器都会添加一个默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="8e2ff-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="8e2ff-114">此未命名的命名空间（有时被称为全局命名空间）存在于每个文件中。</span><span class="sxs-lookup"><span data-stu-id="8e2ff-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="8e2ff-115">全局命名空间中的任何标识符都可用于已命名的命名空间。</span><span class="sxs-lookup"><span data-stu-id="8e2ff-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="8e2ff-116">命名空间隐式具有公共访问权限，这是不可修改的。</span><span class="sxs-lookup"><span data-stu-id="8e2ff-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="8e2ff-117">有关可以分配给命名空间中元素的访问修饰符的讨论，请参阅[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="8e2ff-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="8e2ff-118">可以在两个或多个声明中定义一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="8e2ff-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="8e2ff-119">例如，以下示例将两个类定义为 `MyCompany` 命名空间的一部分：</span><span class="sxs-lookup"><span data-stu-id="8e2ff-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="8e2ff-120">示例</span><span class="sxs-lookup"><span data-stu-id="8e2ff-120">Example</span></span>  
 <span data-ttu-id="8e2ff-121">以下示例显示如何在嵌套命名空间中调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="8e2ff-121">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]  
  
## <a name="for-more-information"></a><span data-ttu-id="8e2ff-122">更多信息</span><span class="sxs-lookup"><span data-stu-id="8e2ff-122">For More Information</span></span>  
 <span data-ttu-id="8e2ff-123">有关使用命名空间的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="8e2ff-123">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="8e2ff-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="8e2ff-124">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="8e2ff-125">使用命名空间</span><span class="sxs-lookup"><span data-stu-id="8e2ff-125">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="8e2ff-126">如何：使用全局命名空间别名</span><span class="sxs-lookup"><span data-stu-id="8e2ff-126">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="8e2ff-127">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="8e2ff-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e2ff-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e2ff-128">See Also</span></span>  
 [<span data-ttu-id="8e2ff-129">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8e2ff-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8e2ff-130">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8e2ff-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8e2ff-131">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="8e2ff-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8e2ff-132">命名空间关键字</span><span class="sxs-lookup"><span data-stu-id="8e2ff-132">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="8e2ff-133">using</span><span class="sxs-lookup"><span data-stu-id="8e2ff-133">using</span></span>](../../../csharp/language-reference/keywords/using.md)
