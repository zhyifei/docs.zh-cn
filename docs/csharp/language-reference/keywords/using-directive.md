---
title: using 指令（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 180c038987e7de6b39a8eae0e86871eea41a40bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="212d1-102">using 指令（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="212d1-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="212d1-103">`using` 指令有三种用途：</span><span class="sxs-lookup"><span data-stu-id="212d1-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="212d1-104">允许在命名空间中使用类型，这样无需在该命名空间中限定某个类型的使用：</span><span class="sxs-lookup"><span data-stu-id="212d1-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="212d1-105">允许访问类型的静态成员，而无需限定使用类型名称进行访问。</span><span class="sxs-lookup"><span data-stu-id="212d1-105">To allow you to access static members of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="212d1-106">有关详细信息，请参阅 [using static 指令](using-static.md)。</span><span class="sxs-lookup"><span data-stu-id="212d1-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="212d1-107">为命名空间或类型创建别名。</span><span class="sxs-lookup"><span data-stu-id="212d1-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="212d1-108">这称为 *using 别名指令*。</span><span class="sxs-lookup"><span data-stu-id="212d1-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="212d1-109">`using` 关键字还用于创建 using 语句，此类语句有助于确保正确处理 <xref:System.IDisposable> 对象（如文件和字体）。</span><span class="sxs-lookup"><span data-stu-id="212d1-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="212d1-110">有关详细信息，请参阅 [using 语句](../../../csharp/language-reference/keywords/using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="212d1-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="212d1-111">Using Static 类型</span><span class="sxs-lookup"><span data-stu-id="212d1-111">Using Static Type</span></span>  
 <span data-ttu-id="212d1-112">你可以访问类型的静态成员，而无需限定使用类型名称进行访问：</span><span class="sxs-lookup"><span data-stu-id="212d1-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="212d1-113">备注</span><span class="sxs-lookup"><span data-stu-id="212d1-113">Remarks</span></span>  
 <span data-ttu-id="212d1-114">`using` 指令的范围限于显示它的文件。</span><span class="sxs-lookup"><span data-stu-id="212d1-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>  
  
 <span data-ttu-id="212d1-115">创建 `using` 别名，以便更易于将标识符限定为命名空间或类型。</span><span class="sxs-lookup"><span data-stu-id="212d1-115">Create a `using` alias to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="212d1-116">using 别名指令的右侧必须始终是一个完全限定类型，而与前面的 using 指令无关。</span><span class="sxs-lookup"><span data-stu-id="212d1-116">The right side of a using alias directive must always be a fully-qualified type regardless of the using directives that come before it.</span></span>  
  
 <span data-ttu-id="212d1-117">创建 `using` 指令，以便在命名空间中使用类型而不必指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="212d1-117">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="212d1-118">`using` 指令不为你提供对嵌套在指定命名空间中的任何命名空间的访问权限。</span><span class="sxs-lookup"><span data-stu-id="212d1-118">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="212d1-119">命名空间分为两类：用户定义的命名空间和系统定义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="212d1-119">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="212d1-120">用户定义的命名空间是在代码中定义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="212d1-120">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="212d1-121">有关系统定义的命名空间的列表，请参阅 [.NET Framework 类库概述](../../../standard/class-library-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="212d1-121">For a list of the system-defined namespaces, see [.NET Framework Class Library Overview](../../../standard/class-library-overview.md).</span></span>  
  
 <span data-ttu-id="212d1-122">有关在其他程序集中引用方法的示例，请参阅[使用命令行创建和使用程序集](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="212d1-122">For examples on referencing methods in other assemblies, see [Create and Use Assemblies Using the Command Line](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="212d1-123">示例 1</span><span class="sxs-lookup"><span data-stu-id="212d1-123">Example 1</span></span>  
  
 <span data-ttu-id="212d1-124">下面的示例显示如何为命名空间定义和使用 `using` 别名：</span><span class="sxs-lookup"><span data-stu-id="212d1-124">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 <span data-ttu-id="212d1-125">using 别名指令的右侧不能有开放式泛型类型。</span><span class="sxs-lookup"><span data-stu-id="212d1-125">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="212d1-126">例如，不能为 List\<T> 创建 using 别名，但可以为 List\<int> 创建。</span><span class="sxs-lookup"><span data-stu-id="212d1-126">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="212d1-127">示例 2</span><span class="sxs-lookup"><span data-stu-id="212d1-127">Example 2</span></span>  
  
 <span data-ttu-id="212d1-128">下面的示例显示如何为类定义 `using` 指令和 `using` 别名：</span><span class="sxs-lookup"><span data-stu-id="212d1-128">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="212d1-129">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="212d1-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="212d1-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="212d1-130">See Also</span></span>  
 [<span data-ttu-id="212d1-131">C# 参考</span><span class="sxs-lookup"><span data-stu-id="212d1-131">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="212d1-132">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="212d1-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="212d1-133">使用命名空间</span><span class="sxs-lookup"><span data-stu-id="212d1-133">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
 [<span data-ttu-id="212d1-134">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="212d1-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="212d1-135">命名空间关键字</span><span class="sxs-lookup"><span data-stu-id="212d1-135">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="212d1-136">命名空间</span><span class="sxs-lookup"><span data-stu-id="212d1-136">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
 [<span data-ttu-id="212d1-137">using 语句</span><span class="sxs-lookup"><span data-stu-id="212d1-137">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
