---
title: 如何：创建签名的友元程序集 (C#)
ms.date: 07/20/2015
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
ms.openlocfilehash: 8f310055db6899bf315310efc22b67bca2c4500f
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44260001"
---
# <a name="how-to-create-signed-friend-assemblies-c"></a><span data-ttu-id="fe564-102">如何：创建签名的友元程序集 (C#)</span><span class="sxs-lookup"><span data-stu-id="fe564-102">How to: Create Signed Friend Assemblies (C#)</span></span>
<span data-ttu-id="fe564-103">本示例演示如何将友元程序集和具有强名称的程序集一起使用。</span><span class="sxs-lookup"><span data-stu-id="fe564-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="fe564-104">这两种程序集必须都使用强名称。</span><span class="sxs-lookup"><span data-stu-id="fe564-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="fe564-105">尽管本示例中的两种程序集使用相同的密钥，但可以对这两种程序集使用不同的密钥。</span><span class="sxs-lookup"><span data-stu-id="fe564-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="fe564-106">创建签名的程序集和友元程序集</span><span class="sxs-lookup"><span data-stu-id="fe564-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="fe564-107">打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="fe564-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="fe564-108">使用强名称工具，通过以下命令序列生成 keyfile 并显示其公钥。</span><span class="sxs-lookup"><span data-stu-id="fe564-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="fe564-109">有关详细信息，请参阅 [Sn.exe （强名称工具）](../../../../framework/tools/sn-exe-strong-name-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="fe564-109">For more information, see [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
    1.  <span data-ttu-id="fe564-110">生成此示例的强名称密钥，并将其存储在 FriendAssemblies.snk 文件中：</span><span class="sxs-lookup"><span data-stu-id="fe564-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="fe564-111">从 FriendAssemblies.snk 文件中提取公钥，将其放入 FriendAssemblies.publickey 中：</span><span class="sxs-lookup"><span data-stu-id="fe564-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="fe564-112">显示存储在 FriendAssemblies.publickey 文件中的公钥：</span><span class="sxs-lookup"><span data-stu-id="fe564-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="fe564-113">创建一个名为 `friend_signed_A` 的 C# 文件，其中包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="fe564-113">Create a C# file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="fe564-114">该代码使用 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性将 friend_signed_B 声明为友元程序集。</span><span class="sxs-lookup"><span data-stu-id="fe564-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="fe564-115">强名称工具在每次运行时生成新的公钥。</span><span class="sxs-lookup"><span data-stu-id="fe564-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="fe564-116">因此，必须将以下代码中的公钥替换为刚生成的公钥，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="fe564-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```csharp  
    // friend_signed_A.cs  
    // Compile with:   
    // csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    using System.Runtime.CompilerServices;  
  
    [assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")]  
    class Class1  
    {  
        public void Test()  
        {  
            System.Console.WriteLine("Class1.Test");  
            System.Console.ReadLine();  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="fe564-117">使用以下命令编译 friend_signed_A 并为其签名。</span><span class="sxs-lookup"><span data-stu-id="fe564-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```csharp  
    csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    ```  
  
5.  <span data-ttu-id="fe564-118">创建一个名为 `friend_signed_B` 的 C# 文件，并包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="fe564-118">Create a C# file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="fe564-119">由于 friend_signed_A 将 friend_signed_B 指定为友元程序集，因此 friend_signed_B 中的代码可以访问 friend_signed_A 中的 `internal` 类型和成员。</span><span class="sxs-lookup"><span data-stu-id="fe564-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `internal` types and members from friend_signed_A.</span></span> <span data-ttu-id="fe564-120">文件包含以下代码。</span><span class="sxs-lookup"><span data-stu-id="fe564-120">The file contains the following code.</span></span>  
  
    ```csharp  
    // friend_signed_B.cs  
    // Compile with:   
    // csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    public class Program  
    {  
        static void Main()  
        {  
            Class1 inst = new Class1();  
            inst.Test();  
        }  
    }  
    ```  
  
6.  <span data-ttu-id="fe564-121">使用以下命令编译 friend_signed_B 并为其签名。</span><span class="sxs-lookup"><span data-stu-id="fe564-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```csharp  
    csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    ```  
  
     <span data-ttu-id="fe564-122">编译器生成的程序集的名称必须与传递给 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性的友元程序集的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="fe564-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="fe564-123">必须使用 `/out` 编译器选项显式指定输出程序集（.exe 或 .dll）的名称。</span><span class="sxs-lookup"><span data-stu-id="fe564-123">You must explicitly specify the name of the output assembly (.exe or .dll) by using the `/out` compiler option.</span></span>  <span data-ttu-id="fe564-124">有关详细信息，请参阅 [/out（C# 编译器选项）](../../../../csharp/language-reference/compiler-options/out-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="fe564-124">For more information, see [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span></span>  
  
7.  <span data-ttu-id="fe564-125">运行 friend_signed_B.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="fe564-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="fe564-126">程序将打印字符串“Class1.Test”。</span><span class="sxs-lookup"><span data-stu-id="fe564-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="fe564-127">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="fe564-127">.NET Framework Security</span></span>  
 <span data-ttu-id="fe564-128"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性和 <xref:System.Security.Permissions.StrongNameIdentityPermission> 类之间具有相似之处。</span><span class="sxs-lookup"><span data-stu-id="fe564-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="fe564-129">主要区别是，<xref:System.Security.Permissions.StrongNameIdentityPermission> 可以要求安全权限来运行一段特定代码，而 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性控制 `internal` 类型和成员的可见性。</span><span class="sxs-lookup"><span data-stu-id="fe564-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe564-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe564-130">See Also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
- [<span data-ttu-id="fe564-131">程序集和全局程序集缓存 (C#)</span><span class="sxs-lookup"><span data-stu-id="fe564-131">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
- [<span data-ttu-id="fe564-132">友元程序集 (C#)</span><span class="sxs-lookup"><span data-stu-id="fe564-132">Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
- [<span data-ttu-id="fe564-133">如何：创建未签名的友元程序集 (C#)</span><span class="sxs-lookup"><span data-stu-id="fe564-133">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
- [<span data-ttu-id="fe564-134">/keyfile</span><span class="sxs-lookup"><span data-stu-id="fe564-134">/keyfile</span></span>](../../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)  
- [<span data-ttu-id="fe564-135">Sn.exe（强名称工具）</span><span class="sxs-lookup"><span data-stu-id="fe564-135">Sn.exe (Strong Name Tool)</span></span>](../../../../framework/tools/sn-exe-strong-name-tool.md)  
- [<span data-ttu-id="fe564-136">创建和使用具有强名称的程序集</span><span class="sxs-lookup"><span data-stu-id="fe564-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
- [<span data-ttu-id="fe564-137">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fe564-137">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
