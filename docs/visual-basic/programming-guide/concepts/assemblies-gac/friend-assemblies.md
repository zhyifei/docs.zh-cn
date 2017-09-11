---
title: "友元程序集 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 23c9167bf6a632b53202bdc56aebb2248065e967
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="friend-assemblies-visual-basic"></a><span data-ttu-id="76f9f-102">友元程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76f9f-102">Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="76f9f-103">一个*友元程序集*是可以访问其他程序集的程序集[朋友](../../../../visual-basic/language-reference/modifiers/friend.md)类型和成员。</span><span class="sxs-lookup"><span data-stu-id="76f9f-103">A *friend assembly* is an assembly that can access another assembly's [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) types and members.</span></span> <span data-ttu-id="76f9f-104">如果您发现一个程序集作为友元程序集，您不再需要标记类型和成员为公共，以使其可由其他程序集访问。</span><span class="sxs-lookup"><span data-stu-id="76f9f-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="76f9f-105">这是在以下方案中特别方便︰</span><span class="sxs-lookup"><span data-stu-id="76f9f-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="76f9f-106">在单元测试，测试代码在运行时单独的程序集，但需要访问所测试程序集中的成员标记为`Friend`。</span><span class="sxs-lookup"><span data-stu-id="76f9f-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `Friend`.</span></span>  
  
-   <span data-ttu-id="76f9f-107">当您正在开发类库和库的新增功能包含在单独的程序集，但需要访问的成员的现有程序集中标记为`Friend`。</span><span class="sxs-lookup"><span data-stu-id="76f9f-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `Friend`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76f9f-108">备注</span><span class="sxs-lookup"><span data-stu-id="76f9f-108">Remarks</span></span>  
 <span data-ttu-id="76f9f-109">您可以使用<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性来标识给定程序集的一个或多个友元程序集。</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="76f9f-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="76f9f-110">下面的示例使用<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性集 A 中，指定程序集`AssemblyB`作为友元程序集。</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="76f9f-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="76f9f-111">这样，程序集`AssemblyB`访问所有类型和成员的程序集标记为`Friend`。</span><span class="sxs-lookup"><span data-stu-id="76f9f-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `Friend`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76f9f-112">当编译的程序集 (程序集`AssemblyB`)，将访问内部类型或内部成员的另一个程序集 (程序集*A*)，您必须显式指定输出文件 （.exe 或.dll） 的名称，通过使用**/out**编译器选项。</span><span class="sxs-lookup"><span data-stu-id="76f9f-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="76f9f-113">这是必需的因为编译器不生成在它所绑定到外部引用时生成的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="76f9f-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="76f9f-114">有关详细信息，请参阅[/输出 (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/out.md)。</span><span class="sxs-lookup"><span data-stu-id="76f9f-114">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports System  
<Assembly: InternalsVisibleTo("AssemblyB")>   
  
' Friend class.  
Friend Class FriendClass  
    Public Sub Test()  
        Console.WriteLine("Sample Class")  
    End Sub  
End Class  
  
' Public class with a Friend method.  
Public Class ClassWithFriendMethod  
    Friend Sub Test()  
        Console.WriteLine("Sample Method")  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="76f9f-115">只有您显式指定与朋友可以访问的程序集`Friend`类型和成员。</span><span class="sxs-lookup"><span data-stu-id="76f9f-115">Only assemblies that you explicitly specify as friends can access `Friend` types and members.</span></span> <span data-ttu-id="76f9f-116">例如，如果程序集 B 的友元程序集 A 和程序集 C 引用程序集 B，C 没有对访问`Friend`A.中的类型</span><span class="sxs-lookup"><span data-stu-id="76f9f-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `Friend` types in A.</span></span>  
  
 <span data-ttu-id="76f9f-117">编译器执行的友元程序集名称传递给一些基本验证<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性。</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="76f9f-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="76f9f-118">如果程序集*A*声明*B*作为友元程序集的验证规则是，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="76f9f-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="76f9f-119">如果程序集*A*具有强名称程序集*B*还必须具有强名称。</span><span class="sxs-lookup"><span data-stu-id="76f9f-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="76f9f-120">传递给特性的友元程序集名称必须包含程序集名称和用于程序集签名的强名称密钥的公钥*B*。</span><span class="sxs-lookup"><span data-stu-id="76f9f-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="76f9f-121">友元程序集名称传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性不能是程序集的强名称*B*︰ 不包括程序集版本、 区域性、 体系结构或公钥标记。</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="76f9f-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="76f9f-122">如果程序集*A*不具有强名称，友元程序集名称应仅包含程序集名称。</span><span class="sxs-lookup"><span data-stu-id="76f9f-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="76f9f-123">有关详细信息，请参阅[如何︰ 创建未签名友元程序集 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="76f9f-123">For more information, see [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="76f9f-124">如果程序集*B*具有强名称，必须指定程序集的强名称密钥*B*通过项目设置或命令行`/keyfile`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="76f9f-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="76f9f-125">有关详细信息，请参阅[如何︰ 创建签名的友元程序集 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="76f9f-125">For more information, see [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="76f9f-126"><xref:System.Security.Permissions.StrongNameIdentityPermission>类还提供了共享类型，具有以下差异的能力︰</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="76f9f-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="76f9f-127"><xref:System.Security.Permissions.StrongNameIdentityPermission>应用于单个类型，而友元程序集应用于整个程序集。</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="76f9f-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="76f9f-128">如果有数百个程序集中的类型*A*想要与程序集共享*B*，您必须添加<xref:System.Security.Permissions.StrongNameIdentityPermission>访问所有这些。</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="76f9f-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="76f9f-129">如果您使用友元程序集，只需一次声明友元关系。</span><span class="sxs-lookup"><span data-stu-id="76f9f-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="76f9f-130">如果您使用<xref:System.Security.Permissions.StrongNameIdentityPermission>，您想要共享的类型必须声明为公共。</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="76f9f-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="76f9f-131">如果您使用友元程序集，共享的类型被声明为`Friend`。</span><span class="sxs-lookup"><span data-stu-id="76f9f-131">If you use a friend assembly, the shared types are declared as `Friend`.</span></span>  
  
 <span data-ttu-id="76f9f-132">有关如何访问程序集的信息`Friend`类型和方法从模块文件 （扩展名为.netmodule 文件），请参阅[/moduleassemblyname (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)。</span><span class="sxs-lookup"><span data-stu-id="76f9f-132">For information about how to access an assembly's `Friend` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f9f-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76f9f-133">See Also</span></span>  
 <span data-ttu-id="76f9f-134"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="76f9f-134"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
 <span data-ttu-id="76f9f-135"><xref:System.Security.Permissions.StrongNameIdentityPermission></xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="76f9f-135"><xref:System.Security.Permissions.StrongNameIdentityPermission></span></span>   
<span data-ttu-id="76f9f-136"> [如何︰ 创建未签名友元程序集 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="76f9f-136"> [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
<span data-ttu-id="76f9f-137"> [如何︰ 创建签名的友元程序集 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="76f9f-137"> [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span></span>  
<span data-ttu-id="76f9f-138"> [程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="76f9f-138"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="76f9f-139"> [编程概念](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="76f9f-139"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
