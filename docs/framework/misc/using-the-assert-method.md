---
title: 使用 Assert 方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- granting permissions, overriding security checks
- code access security, overriding security checks
- overriding security checks
- security [.NET Framework], overriding security checks
- security [.NET Framework], assertions
- asserted permissions
- Assert method
- caller security checks
- permissions [.NET Framework], overriding security checks
- permissions [.NET Framework], assertions
ms.assetid: 1e40f4d3-fb7d-4f19-b334-b6076d469ea9
ms.openlocfilehash: 92e49af78d42f360d5798a72d4e7b981295947e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181107"
---
# <a name="using-the-assert-method"></a>使用 Assert 方法
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <xref:System.Security.CodeAccessPermission.Assert%2A> 是一种可在代码访问权限类和 <xref:System.Security.PermissionSet> 类上调用的方法。 可以使用**Assert**使代码（和下游调用方）执行代码有权执行的操作，但其调用方可能无权执行操作。 安全断言会更改在安全检查期间运行时所执行的正常过程。 断言权限时，它会通知安全系统不检查断言权限的代码的调用方。  
  
> [!CAUTION]
> 请谨慎使用断言，因为它们会打开安全漏洞并破坏运行时强制执行安全限制的机制。  
  
 当库调用非托管代码或所执行的调用需要与库的预期用途不明显关联的权限时，断言非常有用。 例如，调用非托管代码的所有托管代码都必须具有指定**非托管代码**标志**的安全权限**。 默认情况下，如果代码不是来自本地计算机（如从本地 intranet 下载的代码），则不会对其授予此权限。 因此，为了使从本地 intranet 下载的代码能调用使用非托管代码的库，它必须具有由该库断言的权限。 此外，某些库可能会执行对调用方不可见且需要特殊权限的调用。  
  
 在代码以对调用方完全不可见的方式访问资源时，也可使用断言。 例如，假设你的库从数据库获取信息，但在此过程中还会从计算机注册表读取信息。 由于使用库的开发人员无法访问您的源代码，因此他们无法知道他们的代码需要**注册表权限**才能使用您的代码。 在此情况下，如果你决定要求代码调用方有权访问注册表是不合理或不必要的，你可以断言权限以读取注册表。 在此情况下，库应断言权限，以便没有**注册表权限**的调用方可以使用该库。  
  
 仅当断言权限和下游调用方所需的权限属于同一类型且要求的权限是断言权限的子集时，断言才会影响堆栈审核。 例如，如果断言**FileIO 许可**读取 C 驱动器上的所有文件，并且对**FileIO 许可**读取 C：_Temp 中的文件提出了下游要求，则断言可能会影响堆栈遍历;如果断言允许文件在 C 上读取文件，则断言可能会影响堆栈遍历。但是，如果要求**FileIO 许可**写入 C 驱动器，则断言将不起作用。  
  
 若要执行断言，必须向你的代码授予正在断言的权限以及表示有权执行断言的 <xref:System.Security.Permissions.SecurityPermission>。 虽然你可以断言尚未授予代码的权限，但此断言毫无意义，因为安全检查在断言使其成功之前就会失败。  
  
 下图显示了使用**断言**时发生的情况。 假设以下语句针对程序集 A、B、C、E 和 F 以及 P1 和 P1A 两个权限为 true：  
  
- P1A 表示读取 C 驱动器上的 .txt 文件的权限。  
  
- P1 表示读取 C 驱动器上所有文件的权限。  
  
- P1A 和 P1 都是**FileIO 权限**类型，P1A 是 P1 的子集。  
  
- 已向程序集 E 和 F 授予了 P1A 权限。  
  
- 已向程序集 C 授予了 P1 权限。  
  
- 尚未向程序集 A 和 B 授予 P1 或 P1A 权限。  
  
- 方法 A 包含在程序集 A 中，方法 B 包含在程序集 B 中，依次类推。  
  
 ![显示 Assert 方法程序集的图。](./media/using-the-assert-method/assert-method-assemblies.gif)
  
 在这种情况下，方法 A 调用 B、B 调用 C、C 调用 E 和 E 调用 F. 方法 C 主张读取 C 驱动器上的文件的权限（权限 P1），方法 E 请求读取 C 驱动器上的 .txt 文件的权限（权限 P1A）。 在运行时遇到 F 中的需求时，将执行堆栈遍历以检查 F 的所有调用方的权限，从 E. E 开始已被授予 P1A 权限，因此堆栈遍历将继续检查 C 的权限，其中发现 C 的断言。 因为要求的权限 (P1A) 是断言的权限 (P1) 的子集，所以堆栈审核将停止且安全检查会自动成功。 未向程序集 A 和 B 授予权限 P1A 并不重要。 通过断言 P1，方法 C 确保其调用方可以访问受 P1 保护的资源，即使尚未授予调用方访问该资源的权限也是如此。  
  
 如果你设计一个类库且某个类访问受保护的资源，则在大多数情况下，你应该提出安全要求，要求此类的调用方拥有适当的权限。 如果类随后执行一个操作，您知道其大多数调用方将没有权限，并且如果您愿意承担让这些调用方调用代码的责任，则可以通过在表示代码执行的操作的权限对象上调用**Assert**方法来断言权限。 以这种方式使用**Assert**可以让通常无法这样做的调用方调用您的代码。 因此，如果你断言了一个权限，应确保预先执行了适当的安全检查，以防止你的组件被误用。  
  
 例如，假设你的高度受信任的库类具有删除文件的方法。 它通过调用非托管的 Win32 函数来访问文件。 调用方调用代码的**Delete**方法，传入要删除的文件的名称 C：_Test.txt。 在**Delete**方法中，代码将<xref:System.Security.Permissions.FileIOPermission>创建一个表示对 C：_Test.txt 的写入访问权限的对象。 （删除文件需要写入访问权限。然后，代码通过调用**FileIO许可**对象的**Demand**方法调用命令性安全检查。 如果调用堆栈中的某个调用方不具有此权限，则会引发 <xref:System.Security.SecurityException>。 如果未引发任何异常，你会知道所有调用方都有权限访问 C:\Test.txt。 由于您认为大多数调用方将无权访问非托管代码，因此代码随后创建一个<xref:System.Security.Permissions.SecurityPermission>对象，表示调用非托管代码并调用对象的**Assert**方法的权限。 最后，它会调用非托管的 Win32 函数来删除 C:\Text.txt，并将控件返回给调用方。  
  
> [!CAUTION]
> 你必须确保你的代码在以下情况下不使用断言：其他代码可使用你的代码来访问由你正在断言的权限所保护的资源。 例如，在写入其名称由调用方指定为参数的文件的代码中，不会断言**FileIO 许可**以写入文件，因为代码可能会被第三方误用。  
  
 使用命令性安全语法时，在同一方法中的多个权限上调用**Assert**方法会导致引发安全异常。 相反，您应该创建一个**权限集**对象，传递要调用的单个权限，然后在**权限集**对象上调用**Assert**方法。 使用声明性安全语法时，可以多次调用**Assert**方法。  
  
 下面的示例显示了使用**Assert**方法重写安全检查的声明性语法。 请注意 **，FileIOEe属性**语法采用两个<xref:System.Security.Permissions.SecurityAction>值：枚举和要授予权限的文件或目录的位置。 对**Assert**的调用会导致访问`C:\Log.txt`成功，即使未检查调用方访问文件的权限。  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
  
      End Sub  
  
     <FileIOPermission(SecurityAction.Assert, All := "C:\Log.txt")> Public Sub
      MakeLog()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now) '  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {
      }
      [FileIOPermission(SecurityAction.Assert, All = @"C:\Log.txt")]  
      public void MakeLog()  
      {
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}
```  
  
 以下代码片段显示了使用**Assert**方法重写安全检查的必用语法。 在此示例中，声明**FileIO许可**对象的实例。 其构造函数传递**FileIOAccess.AllAccess**来定义允许的访问类型，然后是描述文件位置的字符串。 定义**FileIO许可**对象后，只需调用其**Assert**方法来覆盖安全检查。  
  
```vb  
Option Explicit  
Option Strict  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
      End Sub 'New  
  
      Public Sub MakeLog()  
         Dim FilePermission As New FileIOPermission(FileIOPermissionAccess.AllAccess, "C:\Log.txt")  
         FilePermission.Assert()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now)  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {
      }
      public void MakeLog()  
      {  
         FileIOPermission FilePermission = new FileIOPermission(FileIOPermissionAccess.AllAccess,@"C:\Log.txt");
         FilePermission.Assert();  
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [属性](../../standard/attributes/index.md)
- [代码访问安全性](code-access-security.md)
