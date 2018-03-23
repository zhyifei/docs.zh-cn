---
title: 如何： 创建签名的友元程序集 (Visual Basic)
ms.custom: ''
ms.date: 03/14/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fd9521a87a985cbdeff1616c3070c822892b6e5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="6f877-102">如何： 创建签名的友元程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f877-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="6f877-103">本示例演示如何将友元程序集和具有强名称的程序集一起使用。</span><span class="sxs-lookup"><span data-stu-id="6f877-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="6f877-104">这两种程序集必须都使用强名称。</span><span class="sxs-lookup"><span data-stu-id="6f877-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="6f877-105">尽管本示例中的两种程序集使用相同的密钥，但可以对这两种程序集使用不同的密钥。</span><span class="sxs-lookup"><span data-stu-id="6f877-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="6f877-106">创建签名的程序集和友元程序集</span><span class="sxs-lookup"><span data-stu-id="6f877-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="6f877-107">打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="6f877-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="6f877-108">使用强名称工具，通过以下命令序列生成 keyfile 并显示其公钥。</span><span class="sxs-lookup"><span data-stu-id="6f877-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="6f877-109">有关详细信息，请参阅 [Sn.exe （强名称工具）][Sn.exe （强名称工具）](../../../../framework/tools/sn-exe-strong-name-tool.md))。</span><span class="sxs-lookup"><span data-stu-id="6f877-109">For more information, see [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
    1.  <span data-ttu-id="6f877-110">生成此示例的强名称密钥，并将其存储在 FriendAssemblies.snk 文件中：</span><span class="sxs-lookup"><span data-stu-id="6f877-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="6f877-111">从 FriendAssemblies.snk 文件中提取公钥，将其放入 FriendAssemblies.publickey 中：</span><span class="sxs-lookup"><span data-stu-id="6f877-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="6f877-112">显示存储在 FriendAssemblies.publickey 文件中的公钥：</span><span class="sxs-lookup"><span data-stu-id="6f877-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="6f877-113">创建名为的 Visual Basic 文件`friend_signed_A`，其中包含下面的代码。</span><span class="sxs-lookup"><span data-stu-id="6f877-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="6f877-114">该代码使用 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性将 friend_signed_B 声明为友元程序集。</span><span class="sxs-lookup"><span data-stu-id="6f877-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="6f877-115">强名称工具在每次运行时生成新的公钥。</span><span class="sxs-lookup"><span data-stu-id="6f877-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="6f877-116">因此，必须将以下代码中的公钥替换为刚生成的公钥，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="6f877-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  <span data-ttu-id="6f877-117">使用以下命令编译 friend_signed_A 并为其签名。</span><span class="sxs-lookup"><span data-stu-id="6f877-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```console  
    Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  <span data-ttu-id="6f877-118">创建名为的 Visual Basic 文件`friend_signed_B`，并包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="6f877-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="6f877-119">由于 friend_signed_A 将 friend_signed_B 指定为友元程序集，因此 friend_signed_B 中的代码可以访问 friend_signed_A 中的 `Friend` 类型和成员。</span><span class="sxs-lookup"><span data-stu-id="6f877-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="6f877-120">文件包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="6f877-120">The file contains the following code.</span></span>  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="6f877-121">使用以下命令编译 friend_signed_B 并为其签名。</span><span class="sxs-lookup"><span data-stu-id="6f877-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```console  
    vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="6f877-122">编译器生成的程序集的名称必须与传递给 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性的友元程序集的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="6f877-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="6f877-123">你可以通过使用显式设置程序集`-out`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="6f877-123">You can explicitly set the assembly by using the `-out` compiler option.</span></span> <span data-ttu-id="6f877-124">有关详细信息，请参阅[-out (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/out.md)。</span><span class="sxs-lookup"><span data-stu-id="6f877-124">For more information, see [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7.  <span data-ttu-id="6f877-125">运行 friend_signed_B.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="6f877-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="6f877-126">该程序显示字符串"Class1.Test"。</span><span class="sxs-lookup"><span data-stu-id="6f877-126">The program displays the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6f877-127">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="6f877-127">.NET Framework Security</span></span>  
 <span data-ttu-id="6f877-128"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性和 <xref:System.Security.Permissions.StrongNameIdentityPermission> 类之间具有相似之处。</span><span class="sxs-lookup"><span data-stu-id="6f877-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="6f877-129">主要区别是，<xref:System.Security.Permissions.StrongNameIdentityPermission> 可以要求安全权限来运行一段特定代码，而 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性控制 `Friend` 类型和成员的可见性。</span><span class="sxs-lookup"><span data-stu-id="6f877-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f877-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f877-130">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="6f877-131">程序集和全局程序集缓存 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f877-131">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="6f877-132">友元程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f877-132">Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="6f877-133">如何： 创建未签名友元程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f877-133">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [<span data-ttu-id="6f877-134">-keyfile</span><span class="sxs-lookup"><span data-stu-id="6f877-134">-keyfile</span></span>](../../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 <span data-ttu-id="6f877-135">[Sn.exe （强名称工具）][Sn.exe （强名称工具）](../../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="6f877-135">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>  
 [<span data-ttu-id="6f877-136">创建和使用具有强名称的程序集</span><span class="sxs-lookup"><span data-stu-id="6f877-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)  
 [<span data-ttu-id="6f877-137">编程概念</span><span class="sxs-lookup"><span data-stu-id="6f877-137">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
