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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08b46d96f9fb950602766639559a375a25747010
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073723"
---
# <a name="using-the-assert-method"></a><span data-ttu-id="6243a-102">使用 Assert 方法</span><span class="sxs-lookup"><span data-stu-id="6243a-102">Using the Assert Method</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="6243a-103"><xref:System.Security.CodeAccessPermission.Assert%2A> 是一种可在代码访问权限类和 <xref:System.Security.PermissionSet> 类上调用的方法。</span><span class="sxs-lookup"><span data-stu-id="6243a-103"><xref:System.Security.CodeAccessPermission.Assert%2A> is a method that can be called on code access permission classes and on the <xref:System.Security.PermissionSet> class.</span></span> <span data-ttu-id="6243a-104">可以使用**Assert**以使你的代码 （和下游调用方） 可以执行你的代码有权执行的操作，但其调用方可能没有执行操作的权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-104">You can use **Assert** to enable your code (and downstream callers) to perform actions that your code has permission to do but its callers might not have permission to do.</span></span> <span data-ttu-id="6243a-105">安全断言会更改在安全检查期间运行时所执行的正常过程。</span><span class="sxs-lookup"><span data-stu-id="6243a-105">A security assertion changes the normal process that the runtime performs during a security check.</span></span> <span data-ttu-id="6243a-106">断言权限时，它会通知安全系统不检查断言权限的代码的调用方。</span><span class="sxs-lookup"><span data-stu-id="6243a-106">When you assert a permission, it tells the security system not to check the callers of your code for the asserted permission.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6243a-107">请谨慎使用断言，因为它们会打开安全漏洞并破坏运行时强制执行安全限制的机制。</span><span class="sxs-lookup"><span data-stu-id="6243a-107">Use assertions carefully because they can open security holes and undermine the runtime's mechanism for enforcing security restrictions.</span></span>  
  
 <span data-ttu-id="6243a-108">当库调用非托管代码或所执行的调用需要与库的预期用途不明显关联的权限时，断言非常有用。</span><span class="sxs-lookup"><span data-stu-id="6243a-108">Assertions are useful in situations in which a library calls into unmanaged code or makes a call that requires a permission that is not obviously related to the library's intended use.</span></span> <span data-ttu-id="6243a-109">例如，所有托管代码调用到非托管代码必须具有**SecurityPermission**与**UnmanagedCode**指定标志。</span><span class="sxs-lookup"><span data-stu-id="6243a-109">For example, all managed code that calls into unmanaged code must have **SecurityPermission** with the **UnmanagedCode** flag specified.</span></span> <span data-ttu-id="6243a-110">默认情况下，如果代码不是来自本地计算机（如从本地 intranet 下载的代码），则不会对其授予此权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-110">Code that does not originate from the local computer, such as code that is downloaded from the local intranet, will not be granted this permission by default.</span></span> <span data-ttu-id="6243a-111">因此，为了使从本地 intranet 下载的代码能调用使用非托管代码的库，它必须具有由该库断言的权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-111">Therefore, in order for code that is downloaded from the local intranet to be able to call a library that uses unmanaged code, it must have the permission asserted by the library.</span></span> <span data-ttu-id="6243a-112">此外，某些库可能会执行对调用方不可见且需要特殊权限的调用。</span><span class="sxs-lookup"><span data-stu-id="6243a-112">Additionally, some libraries might make calls that are unseen to callers and require special permissions.</span></span>  
  
 <span data-ttu-id="6243a-113">在代码以对调用方完全不可见的方式访问资源时，也可使用断言。</span><span class="sxs-lookup"><span data-stu-id="6243a-113">You can also use assertions in situations in which your code accesses a resource in a way that is completely hidden from callers.</span></span> <span data-ttu-id="6243a-114">例如，假设你的库从数据库获取信息，但在此过程中还会从计算机注册表读取信息。</span><span class="sxs-lookup"><span data-stu-id="6243a-114">For example, suppose your library acquires information from a database, but in the process also reads information from the computer registry.</span></span> <span data-ttu-id="6243a-115">使用你的库的开发人员无权访问你的源，因为它们有没有办法知道其代码需要**RegistryPermission**若要使用你的代码。</span><span class="sxs-lookup"><span data-stu-id="6243a-115">Because developers using your library do not have access to your source, they have no way of knowing that their code requires **RegistryPermission** in order to use your code.</span></span> <span data-ttu-id="6243a-116">在此情况下，如果你决定要求代码调用方有权访问注册表是不合理或不必要的，你可以断言权限以读取注册表。</span><span class="sxs-lookup"><span data-stu-id="6243a-116">In this case, if you decide that it is not reasonable or necessary to require that callers of your code have permission to access the registry, you can assert permission for reading the registry.</span></span> <span data-ttu-id="6243a-117">在这种情况下，它是库可以断言权限以使相应的无需该调用方**RegistryPermission**可以使用库。</span><span class="sxs-lookup"><span data-stu-id="6243a-117">In this situation, it is appropriate for the library to assert the permission so that callers without **RegistryPermission** can use the library.</span></span>  
  
 <span data-ttu-id="6243a-118">仅当断言权限和下游调用方所需的权限属于同一类型且要求的权限是断言权限的子集时，断言才会影响堆栈审核。</span><span class="sxs-lookup"><span data-stu-id="6243a-118">The assertion affects the stack walk only if the asserted permission and a permission demanded by a downstream caller are of the same type and if the demanded permission is a subset of the asserted permission.</span></span> <span data-ttu-id="6243a-119">例如，如果你断言**FileIOPermission**读取 C 驱动器，和的下游要求的所有文件以供**FileIOPermission**读取 C:\Temp 中的文件，则断言可能会影响堆栈审核;但是，如果是要求**FileIOPermission**要写入到 C 驱动器，则断言会产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="6243a-119">For example, if you assert **FileIOPermission** to read all files on the C drive, and a downstream demand is made for **FileIOPermission** to read files in C:\Temp, the assertion could affect the stack walk; however, if the demand was for **FileIOPermission** to write to the C drive, the assertion would have no effect.</span></span>  
  
 <span data-ttu-id="6243a-120">若要执行断言，必须向你的代码授予正在断言的权限以及表示有权执行断言的 <xref:System.Security.Permissions.SecurityPermission>。</span><span class="sxs-lookup"><span data-stu-id="6243a-120">To perform assertions, your code must be granted both the permission you are asserting and the <xref:System.Security.Permissions.SecurityPermission> that represents the right to make assertions.</span></span> <span data-ttu-id="6243a-121">虽然你可以断言尚未授予代码的权限，但此断言毫无意义，因为安全检查在断言使其成功之前就会失败。</span><span class="sxs-lookup"><span data-stu-id="6243a-121">Although you could assert a permission that your code has not been granted, the assertion would be pointless because the security check would fail before the assertion could cause it to succeed.</span></span>  
  
 <span data-ttu-id="6243a-122">下图显示了在使用时，会发生什么情况**Assert**。</span><span class="sxs-lookup"><span data-stu-id="6243a-122">The following illustration shows what happens when you use **Assert**.</span></span> <span data-ttu-id="6243a-123">假设以下语句针对程序集 A、B、C、E 和 F 以及 P1 和 P1A 两个权限为 true：</span><span class="sxs-lookup"><span data-stu-id="6243a-123">Assume that the following statements are true about assemblies A, B, C, E, and F, and two permissions, P1 and P1A:</span></span>  
  
-   <span data-ttu-id="6243a-124">P1A 表示读取 C 驱动器上的 .txt 文件的权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-124">P1A represents the right to read .txt files on the C drive.</span></span>  
  
-   <span data-ttu-id="6243a-125">P1 表示读取 C 驱动器上所有文件的权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-125">P1 represents the right to read all files on the C drive.</span></span>  
  
-   <span data-ttu-id="6243a-126">P1A 和 P1 都**FileIOPermission**类型，且 P1A 是 P1 的子集。</span><span class="sxs-lookup"><span data-stu-id="6243a-126">P1A and P1 are both **FileIOPermission** types, and P1A is a subset of P1.</span></span>  
  
-   <span data-ttu-id="6243a-127">已向程序集 E 和 F 授予了 P1A 权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-127">Assemblies E and F have been granted P1A permission.</span></span>  
  
-   <span data-ttu-id="6243a-128">已向程序集 C 授予了 P1 权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-128">Assembly C has been granted P1 permission.</span></span>  
  
-   <span data-ttu-id="6243a-129">尚未向程序集 A 和 B 授予 P1 或 P1A 权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-129">Assemblies A and B have been granted neither P1 nor P1A permissions.</span></span>  
  
-   <span data-ttu-id="6243a-130">方法 A 包含在程序集 A 中，方法 B 包含在程序集 B 中，依次类推。</span><span class="sxs-lookup"><span data-stu-id="6243a-130">Method A is contained in assembly A, method B is contained in assembly B, and so on.</span></span>  
  
 ![显示断言方法程序集的关系图。](./media/using-the-assert-method/assert-method-assemblies.gif)    
  
 <span data-ttu-id="6243a-132">在此方案中，方法 A 调用 B，B 调用 C、 C 调用 E、 E 调用 f。 方法 C 断言权限来读取 C 驱动器 （权限 P1） 上的文件，方法 E 要求权限以读取 C 驱动器 （权限 P1A） 上的.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="6243a-132">In this scenario, method A calls B, B calls C, C calls E, and E calls F. Method C asserts permission to read files on the C drive (permission P1), and method E demands permission to read .txt files on the C drive (permission P1A).</span></span> <span data-ttu-id="6243a-133">当在运行时遇到 F 中的要求时，执行堆栈审核检查 F 的所有调用方的权限从 E 开始已授予 P1A 权限，因此堆栈遍历继续探讨的 C，其中发现 C 的断言的权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-133">When the demand in F is encountered at run time, a stack walk is performed to check the permissions of all callers of F, starting with E. E has been granted P1A permission, so the stack walk proceeds to examine the permissions of C, where C's assertion is discovered.</span></span> <span data-ttu-id="6243a-134">因为要求的权限 (P1A) 是断言的权限 (P1) 的子集，所以堆栈审核将停止且安全检查会自动成功。</span><span class="sxs-lookup"><span data-stu-id="6243a-134">Because the demanded permission (P1A) is a subset of the asserted permission (P1), the stack walk stops and the security check automatically succeeds.</span></span> <span data-ttu-id="6243a-135">未向程序集 A 和 B 授予权限 P1A 并不重要。</span><span class="sxs-lookup"><span data-stu-id="6243a-135">It does not matter that assemblies A and B have not been granted permission P1A.</span></span> <span data-ttu-id="6243a-136">通过断言 P1，方法 C 确保其调用方可以访问受 P1 保护的资源，即使尚未授予调用方访问该资源的权限也是如此。</span><span class="sxs-lookup"><span data-stu-id="6243a-136">By asserting P1, method C ensures that its callers can access the resource protected by P1, even if the callers have not been granted permission to access that resource.</span></span>  
  
 <span data-ttu-id="6243a-137">如果你设计一个类库且某个类访问受保护的资源，则在大多数情况下，你应该提出安全要求，要求此类的调用方拥有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-137">If you design a class library and a class accesses a protected resource, you should, in most cases, make a security demand requiring that the callers of the class have the appropriate permission.</span></span> <span data-ttu-id="6243a-138">如果该类随后会执行的操作知道其大多数调用方均方没有相应权限，并且如果您愿意承担责任让这些调用方调用你的代码，你可以断言权限，通过调用**Assert**表示的操作的权限对象上的方法的代码是否执行。</span><span class="sxs-lookup"><span data-stu-id="6243a-138">If the class then performs an operation for which you know most of its callers will not have permission, and if you are willing to take the responsibility for letting these callers call your code, you can assert the permission by calling the **Assert** method on a permission object that represents the operation the code is performing.</span></span> <span data-ttu-id="6243a-139">使用**Assert**允许调用方，因此通常不能以这种方式调用你的代码。</span><span class="sxs-lookup"><span data-stu-id="6243a-139">Using **Assert** in this way lets callers that normally could not do so call your code.</span></span> <span data-ttu-id="6243a-140">因此，如果你断言了一个权限，应确保预先执行了适当的安全检查，以防止你的组件被误用。</span><span class="sxs-lookup"><span data-stu-id="6243a-140">Therefore, if you assert a permission, you should be sure to perform appropriate security checks beforehand to prevent your component from being misused.</span></span>  
  
 <span data-ttu-id="6243a-141">例如，假设你的高度受信任的库类具有删除文件的方法。</span><span class="sxs-lookup"><span data-stu-id="6243a-141">For example, suppose your highly trusted library class has a method that deletes files.</span></span> <span data-ttu-id="6243a-142">它通过调用非托管的 Win32 函数来访问文件。</span><span class="sxs-lookup"><span data-stu-id="6243a-142">It accesses the file by calling an unmanaged Win32 function.</span></span> <span data-ttu-id="6243a-143">调用方调用你的代码**删除**方法，传递要删除的文件的名称 C:\Test.txt。</span><span class="sxs-lookup"><span data-stu-id="6243a-143">A caller invokes your code's **Delete** method, passing in the name of the file to be deleted, C:\Test.txt.</span></span> <span data-ttu-id="6243a-144">内**删除**方法时，你的代码创建<xref:System.Security.Permissions.FileIOPermission>对象，表示对 C:\Test.txt 的写访问权限。</span><span class="sxs-lookup"><span data-stu-id="6243a-144">Within the **Delete** method, your code creates a <xref:System.Security.Permissions.FileIOPermission> object representing write access to C:\Test.txt.</span></span> <span data-ttu-id="6243a-145">（需要写权限来删除文件。）你的代码然后调用命令性安全检查通过调用**FileIOPermission**对象的**需**方法。</span><span class="sxs-lookup"><span data-stu-id="6243a-145">(Write access is required to delete a file.) Your code then invokes an imperative security check by calling the **FileIOPermission** object's **Demand** method.</span></span> <span data-ttu-id="6243a-146">如果调用堆栈中的某个调用方不具有此权限，则会引发 <xref:System.Security.SecurityException>。</span><span class="sxs-lookup"><span data-stu-id="6243a-146">If one of the callers in the call stack does not have this permission, a <xref:System.Security.SecurityException> is thrown.</span></span> <span data-ttu-id="6243a-147">如果未引发任何异常，你会知道所有调用方都有权限访问 C:\Test.txt。</span><span class="sxs-lookup"><span data-stu-id="6243a-147">If no exception is thrown, you know that all callers have the right to access C:\Test.txt.</span></span> <span data-ttu-id="6243a-148">由于您确信大多数调用方没有权限访问非托管的代码，然后创建你的代码<xref:System.Security.Permissions.SecurityPermission>对象，表示有权调用非托管的代码并调用该对象的**Assert**方法。</span><span class="sxs-lookup"><span data-stu-id="6243a-148">Because you believe that most of your callers will not have permission to access unmanaged code, your code then creates a <xref:System.Security.Permissions.SecurityPermission> object that represents the right to call unmanaged code and calls the object's **Assert** method.</span></span> <span data-ttu-id="6243a-149">最后，它会调用非托管的 Win32 函数来删除 C:\Text.txt，并将控件返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="6243a-149">Finally, it calls the unmanaged Win32 function to delete C:\Text.txt and returns control to the caller.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6243a-150">你必须确保你的代码在以下情况下不使用断言：其他代码可使用你的代码来访问由你正在断言的权限所保护的资源。</span><span class="sxs-lookup"><span data-stu-id="6243a-150">You must be sure that your code does not use assertions in situations where your code can be used by other code to access a resource that is protected by the permission you are asserting.</span></span> <span data-ttu-id="6243a-151">例如，在代码中，将写入到其名称由作为参数调用方指定的文件，您将不声明**FileIOPermission**来写入文件，因为你的代码都是由第三方误用。</span><span class="sxs-lookup"><span data-stu-id="6243a-151">For example, in code that writes to a file whose name is specified by the caller as a parameter, you would not assert the **FileIOPermission** for writing to files because your code would be open to misuse by a third party.</span></span>  
  
 <span data-ttu-id="6243a-152">当使用命令性安全语法时，调用**Assert**对同一方法中的多个权限的方法将导致引发安全异常。</span><span class="sxs-lookup"><span data-stu-id="6243a-152">When you use the imperative security syntax, calling the **Assert** method on multiple permissions in the same method causes a security exception to be thrown.</span></span> <span data-ttu-id="6243a-153">相反，应创建**PermissionSet**对象，将其传递要调用，然后调用的各个权限**Assert**方法**PermissionSet**对象。</span><span class="sxs-lookup"><span data-stu-id="6243a-153">Instead, you should create a **PermissionSet** object, pass it the individual permissions you want to invoke, and then call the **Assert** method on the **PermissionSet** object.</span></span> <span data-ttu-id="6243a-154">您可以调用**Assert**比一次使用声明性安全语法更多的方法。</span><span class="sxs-lookup"><span data-stu-id="6243a-154">You can call the **Assert** method more than once when you use the declarative security syntax.</span></span>  
  
 <span data-ttu-id="6243a-155">下面的示例演示声明性语法来重写安全检查使用的**Assert**方法。</span><span class="sxs-lookup"><span data-stu-id="6243a-155">The following example shows declarative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="6243a-156">请注意， **FileIOPermissionAttribute**语法采用两个值：<xref:System.Security.Permissions.SecurityAction>枚举与文件或目录的权限是要对其授予的位置。</span><span class="sxs-lookup"><span data-stu-id="6243a-156">Notice that the **FileIOPermissionAttribute** syntax takes two values: a <xref:System.Security.Permissions.SecurityAction> enumeration and the location of the file or directory to which permission is to be granted.</span></span> <span data-ttu-id="6243a-157">在调用**Assert**导致各要求访问`C:\Log.txt`成功，即使调用方未检查的权限访问该文件。</span><span class="sxs-lookup"><span data-stu-id="6243a-157">The call to **Assert** causes demands for access to `C:\Log.txt` to succeed, even though callers are not checked for permission to access the file.</span></span>  
  
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
  
 <span data-ttu-id="6243a-158">以下代码片段显示重写安全检查使用命令性语法**Assert**方法。</span><span class="sxs-lookup"><span data-stu-id="6243a-158">The following code fragments show imperative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="6243a-159">在此示例中，实例**FileIOPermission**声明对象。</span><span class="sxs-lookup"><span data-stu-id="6243a-159">In this example, an instance of the **FileIOPermission** object is declared.</span></span> <span data-ttu-id="6243a-160">其构造函数传递**FileIOPermissionAccess.AllAccess**以定义的允许，访问类型后, 跟描述文件的位置的字符串。</span><span class="sxs-lookup"><span data-stu-id="6243a-160">Its constructor is passed **FileIOPermissionAccess.AllAccess** to define the type of access allowed, followed by a string describing the file's location.</span></span> <span data-ttu-id="6243a-161">一次**FileIOPermission**定义对象，只需调用其**Assert**方法重写安全检查。</span><span class="sxs-lookup"><span data-stu-id="6243a-161">Once the **FileIOPermission** object is defined, you only need to call its **Assert** method to override the security check.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6243a-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="6243a-162">See also</span></span>

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [<span data-ttu-id="6243a-163">属性</span><span class="sxs-lookup"><span data-stu-id="6243a-163">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- [<span data-ttu-id="6243a-164">代码访问安全性</span><span class="sxs-lookup"><span data-stu-id="6243a-164">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
