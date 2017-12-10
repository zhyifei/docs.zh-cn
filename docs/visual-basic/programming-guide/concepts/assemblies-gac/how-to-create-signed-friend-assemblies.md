---
title: "如何： 创建签名的友元程序集 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e549eeb67c41b3172dd5a5885d59aa6069716a0
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a>如何： 创建签名的友元程序集 (Visual Basic)
本示例演示如何将友元程序集和具有强名称的程序集一起使用。 这两种程序集必须都使用强名称。 尽管本示例中的两种程序集使用相同的密钥，但可以对这两种程序集使用不同的密钥。  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>创建签名的程序集和友元程序集  
  
1.  打开命令提示。  
  
2.  使用强名称工具，通过以下命令序列生成 keyfile 并显示其公钥。 有关详细信息，请参阅 [Sn.exe （强名称工具）](https://msdn.microsoft.com/library/k5b5tt23)。  
  
    1.  生成此示例的强名称密钥，并将其存储在 FriendAssemblies.snk 文件中：  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  从 FriendAssemblies.snk 文件中提取公钥，将其放入 FriendAssemblies.publickey 中：  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  显示存储在 FriendAssemblies.publickey 文件中的公钥：  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  创建名为的 Visual Basic 文件`friend_signed_A`，其中包含下面的代码。 该代码使用 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性将 friend_signed_B 声明为友元程序集。  
  
     强名称工具在每次运行时生成新的公钥。 因此，必须将以下代码中的公钥替换为刚生成的公钥，如以下示例所示。  
  
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
  
4.  使用以下命令编译 friend_signed_A 并为其签名。  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  创建名为的 Visual Basic 文件`friend_signed_B`，并包含以下代码。 由于 friend_signed_A 将 friend_signed_B 指定为友元程序集，因此 friend_signed_B 中的代码可以访问 friend_signed_A 中的 `Friend` 类型和成员。 文件包含以下代码。  
  
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
  
6.  使用以下命令编译 friend_signed_B 并为其签名。  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     编译器生成的程序集的名称必须与传递给 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性的友元程序集的名称匹配。 你可以通过使用显式设置程序集`/out`编译器选项。 有关详细信息，请参阅[(Visual Basic 中) 的 /out](../../../../visual-basic/reference/command-line-compiler/out.md)。  
  
7.  运行 friend_signed_B.exe 文件。  
  
     程序将打印字符串“Class1.Test”。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性和 <xref:System.Security.Permissions.StrongNameIdentityPermission> 类之间具有相似之处。 主要区别是，<xref:System.Security.Permissions.StrongNameIdentityPermission> 可以要求安全权限来运行一段特定代码，而 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性控制 `Friend` 类型和成员的可见性。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [友元程序集 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [如何： 创建未签名友元程序集 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [Sn.exe（强名称工具）](https://msdn.microsoft.com/library/k5b5tt23)  
 [创建和使用具有强名称的程序集](../../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 [编程概念](../../../../visual-basic/programming-guide/concepts/index.md)
