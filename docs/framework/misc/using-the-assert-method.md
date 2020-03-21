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
# <a name="using-the-assert-method"></a><span data-ttu-id="b0041-102">使用 Assert 方法</span><span class="sxs-lookup"><span data-stu-id="b0041-102">Using the Assert Method</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="b0041-103"><xref:System.Security.CodeAccessPermission.Assert%2A> 是一种可在代码访问权限类和 <xref:System.Security.PermissionSet> 类上调用的方法。</span><span class="sxs-lookup"><span data-stu-id="b0041-103"><xref:System.Security.CodeAccessPermission.Assert%2A> is a method that can be called on code access permission classes and on the <xref:System.Security.PermissionSet> class.</span></span> <span data-ttu-id="b0041-104">可以使用**Assert**使代码（和下游调用方）执行代码有权执行的操作，但其调用方可能无权执行操作。</span><span class="sxs-lookup"><span data-stu-id="b0041-104">You can use **Assert** to enable your code (and downstream callers) to perform actions that your code has permission to do but its callers might not have permission to do.</span></span> <span data-ttu-id="b0041-105">安全断言会更改在安全检查期间运行时所执行的正常过程。</span><span class="sxs-lookup"><span data-stu-id="b0041-105">A security assertion changes the normal process that the runtime performs during a security check.</span></span> <span data-ttu-id="b0041-106">断言权限时，它会通知安全系统不检查断言权限的代码的调用方。</span><span class="sxs-lookup"><span data-stu-id="b0041-106">When you assert a permission, it tells the security system not to check the callers of your code for the asserted permission.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="b0041-107">请谨慎使用断言，因为它们会打开安全漏洞并破坏运行时强制执行安全限制的机制。</span><span class="sxs-lookup"><span data-stu-id="b0041-107">Use assertions carefully because they can open security holes and undermine the runtime's mechanism for enforcing security restrictions.</span></span>  
  
 <span data-ttu-id="b0041-108">当库调用非托管代码或所执行的调用需要与库的预期用途不明显关联的权限时，断言非常有用。</span><span class="sxs-lookup"><span data-stu-id="b0041-108">Assertions are useful in situations in which a library calls into unmanaged code or makes a call that requires a permission that is not obviously related to the library's intended use.</span></span> <span data-ttu-id="b0041-109">例如，调用非托管代码的所有托管代码都必须具有指定**非托管代码**标志**的安全权限**。</span><span class="sxs-lookup"><span data-stu-id="b0041-109">For example, all managed code that calls into unmanaged code must have **SecurityPermission** with the **UnmanagedCode** flag specified.</span></span> <span data-ttu-id="b0041-110">默认情况下，如果代码不是来自本地计算机（如从本地 intranet 下载的代码），则不会对其授予此权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-110">Code that does not originate from the local computer, such as code that is downloaded from the local intranet, will not be granted this permission by default.</span></span> <span data-ttu-id="b0041-111">因此，为了使从本地 intranet 下载的代码能调用使用非托管代码的库，它必须具有由该库断言的权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-111">Therefore, in order for code that is downloaded from the local intranet to be able to call a library that uses unmanaged code, it must have the permission asserted by the library.</span></span> <span data-ttu-id="b0041-112">此外，某些库可能会执行对调用方不可见且需要特殊权限的调用。</span><span class="sxs-lookup"><span data-stu-id="b0041-112">Additionally, some libraries might make calls that are unseen to callers and require special permissions.</span></span>  
  
 <span data-ttu-id="b0041-113">在代码以对调用方完全不可见的方式访问资源时，也可使用断言。</span><span class="sxs-lookup"><span data-stu-id="b0041-113">You can also use assertions in situations in which your code accesses a resource in a way that is completely hidden from callers.</span></span> <span data-ttu-id="b0041-114">例如，假设你的库从数据库获取信息，但在此过程中还会从计算机注册表读取信息。</span><span class="sxs-lookup"><span data-stu-id="b0041-114">For example, suppose your library acquires information from a database, but in the process also reads information from the computer registry.</span></span> <span data-ttu-id="b0041-115">由于使用库的开发人员无法访问您的源代码，因此他们无法知道他们的代码需要**注册表权限**才能使用您的代码。</span><span class="sxs-lookup"><span data-stu-id="b0041-115">Because developers using your library do not have access to your source, they have no way of knowing that their code requires **RegistryPermission** in order to use your code.</span></span> <span data-ttu-id="b0041-116">在此情况下，如果你决定要求代码调用方有权访问注册表是不合理或不必要的，你可以断言权限以读取注册表。</span><span class="sxs-lookup"><span data-stu-id="b0041-116">In this case, if you decide that it is not reasonable or necessary to require that callers of your code have permission to access the registry, you can assert permission for reading the registry.</span></span> <span data-ttu-id="b0041-117">在此情况下，库应断言权限，以便没有**注册表权限**的调用方可以使用该库。</span><span class="sxs-lookup"><span data-stu-id="b0041-117">In this situation, it is appropriate for the library to assert the permission so that callers without **RegistryPermission** can use the library.</span></span>  
  
 <span data-ttu-id="b0041-118">仅当断言权限和下游调用方所需的权限属于同一类型且要求的权限是断言权限的子集时，断言才会影响堆栈审核。</span><span class="sxs-lookup"><span data-stu-id="b0041-118">The assertion affects the stack walk only if the asserted permission and a permission demanded by a downstream caller are of the same type and if the demanded permission is a subset of the asserted permission.</span></span> <span data-ttu-id="b0041-119">例如，如果断言**FileIO 许可**读取 C 驱动器上的所有文件，并且对**FileIO 许可**读取 C：_Temp 中的文件提出了下游要求，则断言可能会影响堆栈遍历;如果断言允许文件在 C 上读取文件，则断言可能会影响堆栈遍历。但是，如果要求**FileIO 许可**写入 C 驱动器，则断言将不起作用。</span><span class="sxs-lookup"><span data-stu-id="b0041-119">For example, if you assert **FileIOPermission** to read all files on the C drive, and a downstream demand is made for **FileIOPermission** to read files in C:\Temp, the assertion could affect the stack walk; however, if the demand was for **FileIOPermission** to write to the C drive, the assertion would have no effect.</span></span>  
  
 <span data-ttu-id="b0041-120">若要执行断言，必须向你的代码授予正在断言的权限以及表示有权执行断言的 <xref:System.Security.Permissions.SecurityPermission>。</span><span class="sxs-lookup"><span data-stu-id="b0041-120">To perform assertions, your code must be granted both the permission you are asserting and the <xref:System.Security.Permissions.SecurityPermission> that represents the right to make assertions.</span></span> <span data-ttu-id="b0041-121">虽然你可以断言尚未授予代码的权限，但此断言毫无意义，因为安全检查在断言使其成功之前就会失败。</span><span class="sxs-lookup"><span data-stu-id="b0041-121">Although you could assert a permission that your code has not been granted, the assertion would be pointless because the security check would fail before the assertion could cause it to succeed.</span></span>  
  
 <span data-ttu-id="b0041-122">下图显示了使用**断言**时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="b0041-122">The following illustration shows what happens when you use **Assert**.</span></span> <span data-ttu-id="b0041-123">假设以下语句针对程序集 A、B、C、E 和 F 以及 P1 和 P1A 两个权限为 true：</span><span class="sxs-lookup"><span data-stu-id="b0041-123">Assume that the following statements are true about assemblies A, B, C, E, and F, and two permissions, P1 and P1A:</span></span>  
  
- <span data-ttu-id="b0041-124">P1A 表示读取 C 驱动器上的 .txt 文件的权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-124">P1A represents the right to read .txt files on the C drive.</span></span>  
  
- <span data-ttu-id="b0041-125">P1 表示读取 C 驱动器上所有文件的权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-125">P1 represents the right to read all files on the C drive.</span></span>  
  
- <span data-ttu-id="b0041-126">P1A 和 P1 都是**FileIO 权限**类型，P1A 是 P1 的子集。</span><span class="sxs-lookup"><span data-stu-id="b0041-126">P1A and P1 are both **FileIOPermission** types, and P1A is a subset of P1.</span></span>  
  
- <span data-ttu-id="b0041-127">已向程序集 E 和 F 授予了 P1A 权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-127">Assemblies E and F have been granted P1A permission.</span></span>  
  
- <span data-ttu-id="b0041-128">已向程序集 C 授予了 P1 权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-128">Assembly C has been granted P1 permission.</span></span>  
  
- <span data-ttu-id="b0041-129">尚未向程序集 A 和 B 授予 P1 或 P1A 权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-129">Assemblies A and B have been granted neither P1 nor P1A permissions.</span></span>  
  
- <span data-ttu-id="b0041-130">方法 A 包含在程序集 A 中，方法 B 包含在程序集 B 中，依次类推。</span><span class="sxs-lookup"><span data-stu-id="b0041-130">Method A is contained in assembly A, method B is contained in assembly B, and so on.</span></span>  
  
 ![显示 Assert 方法程序集的图。](./media/using-the-assert-method/assert-method-assemblies.gif)
  
 <span data-ttu-id="b0041-132">在这种情况下，方法 A 调用 B、B 调用 C、C 调用 E 和 E 调用 F. 方法 C 主张读取 C 驱动器上的文件的权限（权限 P1），方法 E 请求读取 C 驱动器上的 .txt 文件的权限（权限 P1A）。</span><span class="sxs-lookup"><span data-stu-id="b0041-132">In this scenario, method A calls B, B calls C, C calls E, and E calls F. Method C asserts permission to read files on the C drive (permission P1), and method E demands permission to read .txt files on the C drive (permission P1A).</span></span> <span data-ttu-id="b0041-133">在运行时遇到 F 中的需求时，将执行堆栈遍历以检查 F 的所有调用方的权限，从 E. E 开始已被授予 P1A 权限，因此堆栈遍历将继续检查 C 的权限，其中发现 C 的断言。</span><span class="sxs-lookup"><span data-stu-id="b0041-133">When the demand in F is encountered at run time, a stack walk is performed to check the permissions of all callers of F, starting with E. E has been granted P1A permission, so the stack walk proceeds to examine the permissions of C, where C's assertion is discovered.</span></span> <span data-ttu-id="b0041-134">因为要求的权限 (P1A) 是断言的权限 (P1) 的子集，所以堆栈审核将停止且安全检查会自动成功。</span><span class="sxs-lookup"><span data-stu-id="b0041-134">Because the demanded permission (P1A) is a subset of the asserted permission (P1), the stack walk stops and the security check automatically succeeds.</span></span> <span data-ttu-id="b0041-135">未向程序集 A 和 B 授予权限 P1A 并不重要。</span><span class="sxs-lookup"><span data-stu-id="b0041-135">It does not matter that assemblies A and B have not been granted permission P1A.</span></span> <span data-ttu-id="b0041-136">通过断言 P1，方法 C 确保其调用方可以访问受 P1 保护的资源，即使尚未授予调用方访问该资源的权限也是如此。</span><span class="sxs-lookup"><span data-stu-id="b0041-136">By asserting P1, method C ensures that its callers can access the resource protected by P1, even if the callers have not been granted permission to access that resource.</span></span>  
  
 <span data-ttu-id="b0041-137">如果你设计一个类库且某个类访问受保护的资源，则在大多数情况下，你应该提出安全要求，要求此类的调用方拥有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-137">If you design a class library and a class accesses a protected resource, you should, in most cases, make a security demand requiring that the callers of the class have the appropriate permission.</span></span> <span data-ttu-id="b0041-138">如果类随后执行一个操作，您知道其大多数调用方将没有权限，并且如果您愿意承担让这些调用方调用代码的责任，则可以通过在表示代码执行的操作的权限对象上调用**Assert**方法来断言权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-138">If the class then performs an operation for which you know most of its callers will not have permission, and if you are willing to take the responsibility for letting these callers call your code, you can assert the permission by calling the **Assert** method on a permission object that represents the operation the code is performing.</span></span> <span data-ttu-id="b0041-139">以这种方式使用**Assert**可以让通常无法这样做的调用方调用您的代码。</span><span class="sxs-lookup"><span data-stu-id="b0041-139">Using **Assert** in this way lets callers that normally could not do so call your code.</span></span> <span data-ttu-id="b0041-140">因此，如果你断言了一个权限，应确保预先执行了适当的安全检查，以防止你的组件被误用。</span><span class="sxs-lookup"><span data-stu-id="b0041-140">Therefore, if you assert a permission, you should be sure to perform appropriate security checks beforehand to prevent your component from being misused.</span></span>  
  
 <span data-ttu-id="b0041-141">例如，假设你的高度受信任的库类具有删除文件的方法。</span><span class="sxs-lookup"><span data-stu-id="b0041-141">For example, suppose your highly trusted library class has a method that deletes files.</span></span> <span data-ttu-id="b0041-142">它通过调用非托管的 Win32 函数来访问文件。</span><span class="sxs-lookup"><span data-stu-id="b0041-142">It accesses the file by calling an unmanaged Win32 function.</span></span> <span data-ttu-id="b0041-143">调用方调用代码的**Delete**方法，传入要删除的文件的名称 C：_Test.txt。</span><span class="sxs-lookup"><span data-stu-id="b0041-143">A caller invokes your code's **Delete** method, passing in the name of the file to be deleted, C:\Test.txt.</span></span> <span data-ttu-id="b0041-144">在**Delete**方法中，代码将<xref:System.Security.Permissions.FileIOPermission>创建一个表示对 C：_Test.txt 的写入访问权限的对象。</span><span class="sxs-lookup"><span data-stu-id="b0041-144">Within the **Delete** method, your code creates a <xref:System.Security.Permissions.FileIOPermission> object representing write access to C:\Test.txt.</span></span> <span data-ttu-id="b0041-145">（删除文件需要写入访问权限。然后，代码通过调用**FileIO许可**对象的**Demand**方法调用命令性安全检查。</span><span class="sxs-lookup"><span data-stu-id="b0041-145">(Write access is required to delete a file.) Your code then invokes an imperative security check by calling the **FileIOPermission** object's **Demand** method.</span></span> <span data-ttu-id="b0041-146">如果调用堆栈中的某个调用方不具有此权限，则会引发 <xref:System.Security.SecurityException>。</span><span class="sxs-lookup"><span data-stu-id="b0041-146">If one of the callers in the call stack does not have this permission, a <xref:System.Security.SecurityException> is thrown.</span></span> <span data-ttu-id="b0041-147">如果未引发任何异常，你会知道所有调用方都有权限访问 C:\Test.txt。</span><span class="sxs-lookup"><span data-stu-id="b0041-147">If no exception is thrown, you know that all callers have the right to access C:\Test.txt.</span></span> <span data-ttu-id="b0041-148">由于您认为大多数调用方将无权访问非托管代码，因此代码随后创建一个<xref:System.Security.Permissions.SecurityPermission>对象，表示调用非托管代码并调用对象的**Assert**方法的权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-148">Because you believe that most of your callers will not have permission to access unmanaged code, your code then creates a <xref:System.Security.Permissions.SecurityPermission> object that represents the right to call unmanaged code and calls the object's **Assert** method.</span></span> <span data-ttu-id="b0041-149">最后，它会调用非托管的 Win32 函数来删除 C:\Text.txt，并将控件返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="b0041-149">Finally, it calls the unmanaged Win32 function to delete C:\Text.txt and returns control to the caller.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="b0041-150">你必须确保你的代码在以下情况下不使用断言：其他代码可使用你的代码来访问由你正在断言的权限所保护的资源。</span><span class="sxs-lookup"><span data-stu-id="b0041-150">You must be sure that your code does not use assertions in situations where your code can be used by other code to access a resource that is protected by the permission you are asserting.</span></span> <span data-ttu-id="b0041-151">例如，在写入其名称由调用方指定为参数的文件的代码中，不会断言**FileIO 许可**以写入文件，因为代码可能会被第三方误用。</span><span class="sxs-lookup"><span data-stu-id="b0041-151">For example, in code that writes to a file whose name is specified by the caller as a parameter, you would not assert the **FileIOPermission** for writing to files because your code would be open to misuse by a third party.</span></span>  
  
 <span data-ttu-id="b0041-152">使用命令性安全语法时，在同一方法中的多个权限上调用**Assert**方法会导致引发安全异常。</span><span class="sxs-lookup"><span data-stu-id="b0041-152">When you use the imperative security syntax, calling the **Assert** method on multiple permissions in the same method causes a security exception to be thrown.</span></span> <span data-ttu-id="b0041-153">相反，您应该创建一个**权限集**对象，传递要调用的单个权限，然后在**权限集**对象上调用**Assert**方法。</span><span class="sxs-lookup"><span data-stu-id="b0041-153">Instead, you should create a **PermissionSet** object, pass it the individual permissions you want to invoke, and then call the **Assert** method on the **PermissionSet** object.</span></span> <span data-ttu-id="b0041-154">使用声明性安全语法时，可以多次调用**Assert**方法。</span><span class="sxs-lookup"><span data-stu-id="b0041-154">You can call the **Assert** method more than once when you use the declarative security syntax.</span></span>  
  
 <span data-ttu-id="b0041-155">下面的示例显示了使用**Assert**方法重写安全检查的声明性语法。</span><span class="sxs-lookup"><span data-stu-id="b0041-155">The following example shows declarative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="b0041-156">请注意 **，FileIOEe属性**语法采用两个<xref:System.Security.Permissions.SecurityAction>值：枚举和要授予权限的文件或目录的位置。</span><span class="sxs-lookup"><span data-stu-id="b0041-156">Notice that the **FileIOPermissionAttribute** syntax takes two values: a <xref:System.Security.Permissions.SecurityAction> enumeration and the location of the file or directory to which permission is to be granted.</span></span> <span data-ttu-id="b0041-157">对**Assert**的调用会导致访问`C:\Log.txt`成功，即使未检查调用方访问文件的权限。</span><span class="sxs-lookup"><span data-stu-id="b0041-157">The call to **Assert** causes demands for access to `C:\Log.txt` to succeed, even though callers are not checked for permission to access the file.</span></span>  
  
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
  
 <span data-ttu-id="b0041-158">以下代码片段显示了使用**Assert**方法重写安全检查的必用语法。</span><span class="sxs-lookup"><span data-stu-id="b0041-158">The following code fragments show imperative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="b0041-159">在此示例中，声明**FileIO许可**对象的实例。</span><span class="sxs-lookup"><span data-stu-id="b0041-159">In this example, an instance of the **FileIOPermission** object is declared.</span></span> <span data-ttu-id="b0041-160">其构造函数传递**FileIOAccess.AllAccess**来定义允许的访问类型，然后是描述文件位置的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0041-160">Its constructor is passed **FileIOPermissionAccess.AllAccess** to define the type of access allowed, followed by a string describing the file's location.</span></span> <span data-ttu-id="b0041-161">定义**FileIO许可**对象后，只需调用其**Assert**方法来覆盖安全检查。</span><span class="sxs-lookup"><span data-stu-id="b0041-161">Once the **FileIOPermission** object is defined, you only need to call its **Assert** method to override the security check.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0041-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0041-162">See also</span></span>

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [<span data-ttu-id="b0041-163">属性</span><span class="sxs-lookup"><span data-stu-id="b0041-163">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="b0041-164">代码访问安全性</span><span class="sxs-lookup"><span data-stu-id="b0041-164">Code Access Security</span></span>](code-access-security.md)
