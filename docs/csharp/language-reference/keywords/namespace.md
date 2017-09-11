---
title: "命名空间（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
dev_langs:
- CSharp
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2cef3949d9a41db36406db059218f7a204172ea
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="namespace-c-reference"></a><span data-ttu-id="9564e-102">命名空间（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9564e-102">namespace (C# Reference)</span></span>
<span data-ttu-id="9564e-103">`namespace` 关键字用于声明包含一组相关对象的作用域。</span><span class="sxs-lookup"><span data-stu-id="9564e-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="9564e-104">可以使用命名空间来组织代码元素并创建全局唯一类型。</span><span class="sxs-lookup"><span data-stu-id="9564e-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 <span data-ttu-id="9564e-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9564e-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9564e-106">备注</span><span class="sxs-lookup"><span data-stu-id="9564e-106">Remarks</span></span>  
 <span data-ttu-id="9564e-107">在命名空间中，可以声明一个或多个以下类型：</span><span class="sxs-lookup"><span data-stu-id="9564e-107">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="9564e-108">另一个命名空间</span><span class="sxs-lookup"><span data-stu-id="9564e-108">another namespace</span></span>  
  
-   [<span data-ttu-id="9564e-109">类</span><span class="sxs-lookup"><span data-stu-id="9564e-109">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="9564e-110">接口</span><span class="sxs-lookup"><span data-stu-id="9564e-110">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="9564e-111">struct</span><span class="sxs-lookup"><span data-stu-id="9564e-111">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="9564e-112">enum</span><span class="sxs-lookup"><span data-stu-id="9564e-112">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="9564e-113">委托</span><span class="sxs-lookup"><span data-stu-id="9564e-113">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="9564e-114">无论是否在 C# 源文件中显式声明命名空间，编译器都会添加一个默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="9564e-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="9564e-115">此未命名的命名空间（有时被称为全局命名空间）存在于每个文件中。</span><span class="sxs-lookup"><span data-stu-id="9564e-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="9564e-116">全局命名空间中的任何标识符都可用于已命名的命名空间。</span><span class="sxs-lookup"><span data-stu-id="9564e-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="9564e-117">命名空间隐式具有公共访问权限，这是不可修改的。</span><span class="sxs-lookup"><span data-stu-id="9564e-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="9564e-118">有关可以分配给命名空间中元素的访问修饰符的讨论，请参阅[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="9564e-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="9564e-119">可以在两个或多个声明中定义一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="9564e-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="9564e-120">例如，以下示例将两个类定义为 `MyCompany` 命名空间的一部分：</span><span class="sxs-lookup"><span data-stu-id="9564e-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 <span data-ttu-id="9564e-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9564e-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9564e-122">示例</span><span class="sxs-lookup"><span data-stu-id="9564e-122">Example</span></span>  
 <span data-ttu-id="9564e-123">以下示例显示如何在嵌套命名空间中调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="9564e-123">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 <span data-ttu-id="9564e-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9564e-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="9564e-125">更多信息</span><span class="sxs-lookup"><span data-stu-id="9564e-125">For More Information</span></span>  
 <span data-ttu-id="9564e-126">有关使用命名空间的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="9564e-126">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9564e-127">命名空间</span><span class="sxs-lookup"><span data-stu-id="9564e-127">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="9564e-128">使用命名空间</span><span class="sxs-lookup"><span data-stu-id="9564e-128">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="9564e-129">如何：使用全局命名空间别名</span><span class="sxs-lookup"><span data-stu-id="9564e-129">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="9564e-130">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="9564e-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9564e-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9564e-131">See Also</span></span>  
 <span data-ttu-id="9564e-132">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9564e-132">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9564e-133">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9564e-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9564e-134">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="9564e-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="9564e-135">[命名空间关键字](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="9564e-135">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 [<span data-ttu-id="9564e-136">using</span><span class="sxs-lookup"><span data-stu-id="9564e-136">using</span></span>](../../../csharp/language-reference/keywords/using.md)

