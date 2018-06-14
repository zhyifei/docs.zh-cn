---
title: 友元程序集 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
ms.openlocfilehash: 91bc33f33c4fc34c6e0f3ae197ecd2b876161de3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644376"
---
# <a name="friend-assemblies-visual-basic"></a>友元程序集 (Visual Basic)
A*友元程序集*是可以访问另一个程序集的程序集[友元](../../../../visual-basic/language-reference/modifiers/friend.md)类型和成员。 如果将一个程序集标识为友元程序集，则无需再将类型和成员标记为公共，其他程序集就能访问它们。 此举在下列情境中尤其方便：  
  
-   在单元测试中，在中运行的测试代码时单独的程序集，但需要访问所测试的程序集中的成员标记为`Friend`。  
  
-   当你在开发一个类库，并且添加到库包含在单独的程序集中，但需要访问标记为的现有程序集中的成员`Friend`。  
  
## <a name="remarks"></a>备注  
 可使用 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性标识给定程序集的一个或多个友元程序集。 如下示例使用程序集 A 中的 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性，并将程序集 `AssemblyB` 指定为友元程序集。 这使程序集 `AssemblyB` 能访问标记为 `Friend` 的程序集 A 中的所有类型和成员。  
  
> [!NOTE]
>  在编译将访问另一程序集（程序集 *A*）的内部类型或内部成员的程序集（程序集 `AssemblyB`）时，必须使用 **/out** 编译器选项显式指定输出文件（.exe 或 .dll）的名称。 这是必需的，因为编译器尚未为它在绑定到外部引用时而正在构建的程序集生成名称。 有关详细信息，请参阅[(Visual Basic 中) 的 /out](../../../../visual-basic/reference/command-line-compiler/out.md)。  
  
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
  
 只有显式指定为友元的程序集才能访问 `Friend` 类型和成员。 例如，如果程序集 B 是程序集 A 的友元，且程序集 C 引用了程序集 B，则 C 无法访问 A 中的 `Friend` 类型。  
  
 编译器对传递到 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性的友元程序集名称执行一些基本验证。 如果程序集 *A* 将 *B* 声明为友元程序集，则验证规则如下：  
  
-   如果程序集 *A* 是强名称的程序集，那么程序集 *B* 也必须是强名称的。 传递到特性的友元程序集名称必须包含有程序集名称，和用于对程序集 *B* 签名的强名称密钥的公钥。  
  
     传递到 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性的友元程序集名称不能是程序集 B 的强名称：请勿包含程序集版本、区域性、体系结构或公钥令牌。  
  
-   如果程序集 *A* 不是强名称，则友元程序集名称应仅由程序集名称构成。 有关详细信息，请参阅[如何： 创建未签名友元程序集 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)。  
  
-   如果程序集 *B* 是强名称，则必须使用项目设置或命令行 `/keyfile` 编译器选项为程序集 *B* 指定强名称密钥。 有关详细信息，请参阅[如何： 创建签名友元程序集 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)。  
  
 <xref:System.Security.Permissions.StrongNameIdentityPermission> 类还提供类型共享功能，但具有以下差异：  
  
-   <xref:System.Security.Permissions.StrongNameIdentityPermission> 应用到单个类型，而友元程序集应用到整个程序集。  
  
-   如果要与程序集 B 共享程序集 A 中的数百个类型，则必须向它们全部添加 <xref:System.Security.Permissions.StrongNameIdentityPermission>。 如果使用友元程序集，只需声明友元关系一次。  
  
-   如果使用 <xref:System.Security.Permissions.StrongNameIdentityPermission>，必须将要共享的类型声明为公共类型。 如果使用友元程序集，共享的类型会声明为 `Friend`。  
  
 有关如何访问程序集的信息`Friend`类型和方法从模块文件 （扩展名为.netmodule 文件），请参阅[/moduleassemblyname (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 <xref:System.Security.Permissions.StrongNameIdentityPermission>  
 [如何： 创建未签名友元程序集 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [如何： 创建签名的友元程序集 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [编程概念](../../../../visual-basic/programming-guide/concepts/index.md)
