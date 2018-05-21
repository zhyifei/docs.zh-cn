---
title: 友元程序集 (C#)
ms.date: 07/20/2015
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
ms.openlocfilehash: c9265a6ce53d97f1d0b8aaeb0f1aae3b7b75f2cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="friend-assemblies-c"></a><span data-ttu-id="04117-102">友元程序集 (C#)</span><span class="sxs-lookup"><span data-stu-id="04117-102">Friend Assemblies (C#)</span></span>
<span data-ttu-id="04117-103">友元程序集是可以访问其他程序集的[内部](../../../../csharp/language-reference/keywords/internal.md)类型和成员的程序集。</span><span class="sxs-lookup"><span data-stu-id="04117-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../../../csharp/language-reference/keywords/internal.md) types and members.</span></span> <span data-ttu-id="04117-104">如果将一个程序集标识为友元程序集，则无需再将类型和成员标记为公共，其他程序集就能访问它们。</span><span class="sxs-lookup"><span data-stu-id="04117-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="04117-105">此举在下列情境中尤其方便：</span><span class="sxs-lookup"><span data-stu-id="04117-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="04117-106">在单元测试期间，当测试代码在单独的程序集上运行，但要求访问标记为 `internal` 的正在被测试的程序集中的成员时。</span><span class="sxs-lookup"><span data-stu-id="04117-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` .</span></span>  
  
-   <span data-ttu-id="04117-107">当你正在开发类库，库的添加包含在单独的程序集中，但要求访问标记为 `internal` 的现有程序集中的成员时。</span><span class="sxs-lookup"><span data-stu-id="04117-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` .</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04117-108">备注</span><span class="sxs-lookup"><span data-stu-id="04117-108">Remarks</span></span>  
 <span data-ttu-id="04117-109">可使用 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性标识给定程序集的一个或多个友元程序集。</span><span class="sxs-lookup"><span data-stu-id="04117-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="04117-110">如下示例使用程序集 A 中的 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性，并将程序集 `AssemblyB` 指定为友元程序集。</span><span class="sxs-lookup"><span data-stu-id="04117-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="04117-111">这使程序集 `AssemblyB` 能访问标记为 `internal` 的程序集 A 中的所有类型和成员。</span><span class="sxs-lookup"><span data-stu-id="04117-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `internal`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04117-112">在编译将访问另一程序集（程序集 *A*）的内部类型或内部成员的程序集（程序集 `AssemblyB`）时，必须使用 **/out** 编译器选项显式指定输出文件（.exe 或 .dll）的名称。</span><span class="sxs-lookup"><span data-stu-id="04117-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="04117-113">这是必需的，因为编译器尚未为它在绑定到外部引用时而正在构建的程序集生成名称。</span><span class="sxs-lookup"><span data-stu-id="04117-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="04117-114">有关详细信息，请参阅 [/out (C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="04117-114">For more information, see [/out (C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) .</span></span>  
  
```csharp  
using System.Runtime.CompilerServices;  
using System;  
  
[assembly: InternalsVisibleTo("AssemblyB")]  
  
// The class is internal by default.  
class FriendClass  
{  
    public void Test()  
    {  
        Console.WriteLine("Sample Class");  
    }  
}  
  
// Public class that has an internal method.  
public class ClassWithFriendMethod  
{  
    internal void Test()  
    {  
        Console.WriteLine("Sample Method");  
    }  
  
}  
```  
  
 <span data-ttu-id="04117-115">只有显式指定为友元的程序集才能访问 `internal` 类型和成员。</span><span class="sxs-lookup"><span data-stu-id="04117-115">Only assemblies that you explicitly specify as friends can access `internal` types and members.</span></span> <span data-ttu-id="04117-116">例如，如果程序集 B 是程序集 A 的友元，且程序集 C 引用了程序集 B，则 C 无法访问 A 中的 `internal` 类型。</span><span class="sxs-lookup"><span data-stu-id="04117-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `internal` types in A.</span></span>  
  
 <span data-ttu-id="04117-117">编译器对传递到 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性的友元程序集名称执行一些基本验证。</span><span class="sxs-lookup"><span data-stu-id="04117-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="04117-118">如果程序集 *A* 将 *B* 声明为友元程序集，则验证规则如下：</span><span class="sxs-lookup"><span data-stu-id="04117-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="04117-119">如果程序集 *A* 是强名称的程序集，那么程序集 *B* 也必须是强名称的。</span><span class="sxs-lookup"><span data-stu-id="04117-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="04117-120">传递到特性的友元程序集名称必须包含有程序集名称，和用于对程序集 *B* 签名的强名称密钥的公钥。</span><span class="sxs-lookup"><span data-stu-id="04117-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="04117-121">传递到 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性的友元程序集名称不能是程序集 B 的强名称：请勿包含程序集版本、区域性、体系结构或公钥令牌。</span><span class="sxs-lookup"><span data-stu-id="04117-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="04117-122">如果程序集 *A* 不是强名称，则友元程序集名称应仅由程序集名称构成。</span><span class="sxs-lookup"><span data-stu-id="04117-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="04117-123">有关详细信息，请参阅[如何：创建未签名的友元程序集(C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="04117-123">For more information, see [How to: Create Unsigned Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="04117-124">如果程序集 *B* 是强名称，则必须使用项目设置或命令行 `/keyfile` 编译器选项为程序集 *B* 指定强名称密钥。</span><span class="sxs-lookup"><span data-stu-id="04117-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="04117-125">有关详细信息，请参阅[如何：创建签名的友元程序集(C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="04117-125">For more information, see [How to: Create Signed Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="04117-126"><xref:System.Security.Permissions.StrongNameIdentityPermission> 类还提供类型共享功能，但具有以下差异：</span><span class="sxs-lookup"><span data-stu-id="04117-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="04117-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> 应用到单个类型，而友元程序集应用到整个程序集。</span><span class="sxs-lookup"><span data-stu-id="04117-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="04117-128">如果要与程序集 B 共享程序集 A 中的数百个类型，则必须向它们全部添加 <xref:System.Security.Permissions.StrongNameIdentityPermission>。</span><span class="sxs-lookup"><span data-stu-id="04117-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="04117-129">如果使用友元程序集，只需声明友元关系一次。</span><span class="sxs-lookup"><span data-stu-id="04117-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="04117-130">如果使用 <xref:System.Security.Permissions.StrongNameIdentityPermission>，必须将要共享的类型声明为公共类型。</span><span class="sxs-lookup"><span data-stu-id="04117-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="04117-131">如果使用友元程序集，共享的类型会声明为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="04117-131">If you use a friend assembly, the shared types are declared as `internal`.</span></span>  
  
 <span data-ttu-id="04117-132">有关如何从模块文件（扩展名为 .netmodule 的文件）访问程序集的 `internal` 类型和方法，请参阅 [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="04117-132">For information about how to access an assembly's `internal` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04117-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="04117-133">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 <xref:System.Security.Permissions.StrongNameIdentityPermission>  
 [<span data-ttu-id="04117-134">如何：创建未签名的友元程序集 (C#)</span><span class="sxs-lookup"><span data-stu-id="04117-134">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [<span data-ttu-id="04117-135">如何：创建签名的友元程序集 (C#)</span><span class="sxs-lookup"><span data-stu-id="04117-135">How to: Create Signed Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [<span data-ttu-id="04117-136">程序集和全局程序集缓存 (C#)</span><span class="sxs-lookup"><span data-stu-id="04117-136">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="04117-137">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="04117-137">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
