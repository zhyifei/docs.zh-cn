---
title: 如何：创建 GenericPrincipal 和 GenericIdentity 对象
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Creating Generic Identity Objects
- GenericPrincipal Objects
- Creating GenericPrincipal Objects
- GenericIdentity Objects
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8dd255aafe16cf0cb893ff4157b3590b3fc8d03
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583675"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="2b5b0-102">如何：创建 GenericPrincipal 和 GenericIdentity 对象</span><span class="sxs-lookup"><span data-stu-id="2b5b0-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>
<span data-ttu-id="2b5b0-103">可以使用<xref:System.Security.Principal.GenericIdentity>类结合<xref:System.Security.Principal.GenericPrincipal>类，以创建独立于 Windows 域存在的授权方案。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-103">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>  
  
### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="2b5b0-104">创建 GenericPrincipal 对象</span><span class="sxs-lookup"><span data-stu-id="2b5b0-104">To create a GenericPrincipal object</span></span>  
  
1.  <span data-ttu-id="2b5b0-105">创建标识类的一个新实例，并用希望它持有的名称对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-105">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="2b5b0-106">以下代码创建一个新的 **GenericIdentity** 对象，并用名称 `MyUser` 对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-106">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>  
  
    ```vb  
    Dim myIdentity As New GenericIdentity("MyUser")  
    ```  
  
    ```csharp  
    GenericIdentity myIdentity = new GenericIdentity("MyUser");  
    ```  
  
2.  <span data-ttu-id="2b5b0-107">创建 **GenericPrincipal** 类的一个新实例，并用先前创建的 **GenericIdentity** 对象和表示希望与此主体关联的角色的字符串数组对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-107">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="2b5b0-108">下面的代码示例指定表示一个管理员角色和一个用户角色的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-108">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="2b5b0-109">然后用前面的 **GenericIdentity** 和该字符串数组对 **GenericPrincipal** 进行初始化。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-109">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>  
  
    ```vb  
    Dim myStringArray As String() = {"Manager", "Teller"}  
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)  
    ```  
  
    ```csharp  
    String[] myStringArray = {"Manager", "Teller"};  
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);  
    ```  
  
3.  <span data-ttu-id="2b5b0-110">使用以下代码将主体附加到当前线程中。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-110">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="2b5b0-111">此操作的主体必须验证几次，则必须验证你的应用程序中运行其他代码或必须通过验证的情况下很有用<xref:System.Security.Permissions.PrincipalPermission>对象。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-111">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="2b5b0-112">不将主体附加到线程中，仍可对主体对象执行基于角色的验证。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-112">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="2b5b0-113">有关详细信息，请参阅[替换主体对象](../../../docs/standard/security/replacing-a-principal-object.md)。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-113">For more information, see [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md).</span></span>  
  
    ```vb  
    Thread.CurrentPrincipal = myPrincipal  
    ```  
  
    ```csharp  
    Thread.CurrentPrincipal = myPrincipal;  
    ```  
  
## <a name="example"></a><span data-ttu-id="2b5b0-114">示例</span><span class="sxs-lookup"><span data-stu-id="2b5b0-114">Example</span></span>  
 <span data-ttu-id="2b5b0-115">下面的代码示例说明如何创建 **GenericPrincipal** 和 **GenericIdentity** 的实例。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-115">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="2b5b0-116">此代码将这些对象的值显示到控制台中。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-116">This code displays the values of these objects to the console.</span></span>  
  
```vb  
Imports System  
Imports System.Security.Principal  
Imports System.Threading  
  
Public Class Class1  
  
    Public Shared Sub Main()  
        ' Create generic identity.  
        Dim myIdentity As New GenericIdentity("MyIdentity")  
  
        ' Create generic principal.  
        Dim myStringArray As String() =  {"Manager", "Teller"}  
        Dim myPrincipal As New GenericPrincipal(myIdentity, myStringArray)  
  
        ' Attach the principal to the current thread.  
        ' This is not required unless repeated validation must occur,  
        ' other code in your application must validate, or the   
        ' PrincipalPermisson object is used.   
        Thread.CurrentPrincipal = myPrincipal  
  
        ' Print values to the console.  
        Dim name As String = myPrincipal.Identity.Name  
        Dim auth As Boolean = myPrincipal.Identity.IsAuthenticated  
        Dim isInRole As Boolean = myPrincipal.IsInRole("Manager")  
  
        Console.WriteLine("The name is: {0}", name)  
        Console.WriteLine("The isAuthenticated is: {0}", auth)  
        Console.WriteLine("Is this a Manager? {0}", isInRole)  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Security.Principal;  
using System.Threading;  
  
public class Class1  
{  
    public static int Main(string[] args)  
    {  
    // Create generic identity.  
    GenericIdentity myIdentity = new GenericIdentity("MyIdentity");  
  
    // Create generic principal.  
    String[] myStringArray = {"Manager", "Teller"};  
    GenericPrincipal myPrincipal =   
        new GenericPrincipal(myIdentity, myStringArray);  
  
    // Attach the principal to the current thread.  
    // This is not required unless repeated validation must occur,  
    // other code in your application must validate, or the   
    // PrincipalPermisson object is used.   
    Thread.CurrentPrincipal = myPrincipal;  
  
    // Print values to the console.  
    String name =  myPrincipal.Identity.Name;  
    bool auth =  myPrincipal.Identity.IsAuthenticated;   
    bool isInRole =  myPrincipal.IsInRole("Manager");  
  
    Console.WriteLine("The name is: {0}", name);  
    Console.WriteLine("The isAuthenticated is: {0}", auth);  
    Console.WriteLine("Is this a Manager? {0}", isInRole);  
  
    return 0;  
    }  
}  
```  
  
 <span data-ttu-id="2b5b0-117">执行时，应用程序显示类似于下面这样的输出。</span><span class="sxs-lookup"><span data-stu-id="2b5b0-117">When executed, the application displays output similar to the following.</span></span>  
  
```  
The Name is: MyIdentity  
The IsAuthenticated is: True  
Is this a Manager? True  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b5b0-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b5b0-118">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [<span data-ttu-id="2b5b0-119">替换主体对象</span><span class="sxs-lookup"><span data-stu-id="2b5b0-119">Replacing a Principal Object</span></span>](../../../docs/standard/security/replacing-a-principal-object.md)
- [<span data-ttu-id="2b5b0-120">主体和标识对象</span><span class="sxs-lookup"><span data-stu-id="2b5b0-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
