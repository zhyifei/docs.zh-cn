---
title: "如何︰ 创建签名的友元程序集 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a8a7df331c8cd93de45d902cb9b6c67460952c6d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="68a54-102">如何︰ 创建签名的友元程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a54-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="68a54-103">此示例演示如何对具有强名称的程序集使用友元程序集。</span><span class="sxs-lookup"><span data-stu-id="68a54-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="68a54-104">两个程序集必须具有强名称。</span><span class="sxs-lookup"><span data-stu-id="68a54-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="68a54-105">尽管在此示例中两个程序集使用相同的密钥，但您可以为两个程序集使用不同的密钥。</span><span class="sxs-lookup"><span data-stu-id="68a54-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="68a54-106">若要创建签名的程序集和友元程序集</span><span class="sxs-lookup"><span data-stu-id="68a54-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="68a54-107">打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="68a54-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="68a54-108">下面的命令序列使用强名称工具，以生成密钥文件并显示其公钥。</span><span class="sxs-lookup"><span data-stu-id="68a54-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="68a54-109">有关详细信息，请参阅 [Sn.exe （强名称工具）](https://msdn.microsoft.com/library/k5b5tt23)。</span><span class="sxs-lookup"><span data-stu-id="68a54-109">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
    1.  <span data-ttu-id="68a54-110">生成此示例的强名称密钥，并将其存储在文件 FriendAssemblies.snk:</span><span class="sxs-lookup"><span data-stu-id="68a54-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="68a54-111">从 FriendAssemblies.snk 中提取公钥并将其放入 FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="68a54-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="68a54-112">此时会显示在文件 FriendAssemblies.publickey 中存储的公钥︰</span><span class="sxs-lookup"><span data-stu-id="68a54-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="68a54-113">创建一个名为 Visual Basic 文件`friend_signed_A`，其中包含下面的代码。</span><span class="sxs-lookup"><span data-stu-id="68a54-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="68a54-114">该代码使用<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性声明为友元程序集的 friend_signed_B。</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="68a54-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="68a54-115">每次运行时，强名称工具会生成新的公钥。</span><span class="sxs-lookup"><span data-stu-id="68a54-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="68a54-116">因此，您必须将下面的代码中的公钥替换只是生成的公钥如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="68a54-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  <span data-ttu-id="68a54-117">编译并通过使用以下命令来签署 friend_signed_A。</span><span class="sxs-lookup"><span data-stu-id="68a54-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  <span data-ttu-id="68a54-118">创建名为的 Visual Basic 文件`friend_signed_B`，并包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="68a54-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="68a54-119">由于 friend_signed_A 指定 friend_signed_B 作为友元程序集，所以 friend_signed_B 中的代码可以访问`Friend`类型和从 friend_signed_A 的成员。</span><span class="sxs-lookup"><span data-stu-id="68a54-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="68a54-120">该文件包含下面的代码。</span><span class="sxs-lookup"><span data-stu-id="68a54-120">The file contains the following code.</span></span>  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="68a54-121">编译并通过使用以下命令来签署 friend_signed_B。</span><span class="sxs-lookup"><span data-stu-id="68a54-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="68a54-122">由编译器生成的程序集名称必须与匹配的友元程序集名称传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性。</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="68a54-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="68a54-123">通过使用可以显式设置该程序集`/out`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="68a54-123">You can explicitly set the assembly by using the `/out` compiler option.</span></span> <span data-ttu-id="68a54-124">有关详细信息，请参阅[/输出 (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/out.md)。</span><span class="sxs-lookup"><span data-stu-id="68a54-124">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7.  <span data-ttu-id="68a54-125">运行 friend_signed_B.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="68a54-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="68a54-126">此程序将输出字符串"Class1.Test"。</span><span class="sxs-lookup"><span data-stu-id="68a54-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="68a54-127">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="68a54-127">.NET Framework Security</span></span>  
 <span data-ttu-id="68a54-128"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性和<xref:System.Security.Permissions.StrongNameIdentityPermission>类</xref:System.Security.Permissions.StrongNameIdentityPermission></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>之间有相似之处</span><span class="sxs-lookup"><span data-stu-id="68a54-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="68a54-129">主要区别在于<xref:System.Security.Permissions.StrongNameIdentityPermission>可要求安全权限才能运行的代码中，某个特定部分，而<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性控制的可见性`Friend`类型和成员。</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="68a54-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a54-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68a54-130">See Also</span></span>  
 <span data-ttu-id="68a54-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="68a54-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
<span data-ttu-id="68a54-132"> [程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="68a54-132"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="68a54-133"> [友元程序集 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="68a54-133"> [Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
<span data-ttu-id="68a54-134"> [如何︰ 创建未签名友元程序集 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="68a54-134"> [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
<span data-ttu-id="68a54-135"> [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="68a54-135"> [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="68a54-136"> [Sn.exe （强名称工具）](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="68a54-136"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
<span data-ttu-id="68a54-137"> [创建和使用具有强名称程序集](https://msdn.microsoft.com/library/xwb8f617) </span><span class="sxs-lookup"><span data-stu-id="68a54-137"> [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) </span></span>  
<span data-ttu-id="68a54-138"> [编程概念](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="68a54-138"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
