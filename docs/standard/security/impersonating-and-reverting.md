---
title: 模拟与恢复
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET Framework], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3bc5b4a9bef51ac1591bdeb21651cee624d552b2
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339365"
---
# <a name="impersonating-and-reverting"></a><span data-ttu-id="4492c-102">模拟与恢复</span><span class="sxs-lookup"><span data-stu-id="4492c-102">Impersonating and Reverting</span></span>
<span data-ttu-id="4492c-103">有时可能需要获取 Windows 帐户标记来模拟 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="4492c-103">Sometimes you might need to obtain a Windows account token to impersonate a Windows account.</span></span> <span data-ttu-id="4492c-104">例如，基于 ASP.NET 的应用程序可能需要在不同时间代表多个用户进行工作。</span><span class="sxs-lookup"><span data-stu-id="4492c-104">For example, your ASP.NET-based application might have to act on behalf of several users at different times.</span></span> <span data-ttu-id="4492c-105">应用程序可以从 Internet 信息服务 (IIS) 接受一个表示管理员的标记，模拟该用户，执行一项操作，然后还原到以前的身份。</span><span class="sxs-lookup"><span data-stu-id="4492c-105">Your application might accept a token that represents an administrator from Internet Information Services (IIS), impersonate that user, perform an operation, and revert to the previous identity.</span></span> <span data-ttu-id="4492c-106">然后，可以从 IIS 接受一个表示拥有较少权限的用户的标记，执行某项操作，并再次还原。</span><span class="sxs-lookup"><span data-stu-id="4492c-106">Next, it might accept a token from IIS that represents a user with fewer rights, perform some operation, and revert again.</span></span>  
  
 <span data-ttu-id="4492c-107">如果应用程序必须模拟一个未通过 IIS 附加到当前线程的 Windows 帐户，则必须检索该帐户的标记并用它来激活该帐户。</span><span class="sxs-lookup"><span data-stu-id="4492c-107">In situations where your application must impersonate a Windows account that has not been attached to the current thread by IIS, you must retrieve that account's token and use it to activate the account.</span></span> <span data-ttu-id="4492c-108">通过执行下列任务可实现这一目的：</span><span class="sxs-lookup"><span data-stu-id="4492c-108">You can do this by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="4492c-109">通过调用非托管的 **LogonUser** 方法，检索特定用户的帐户标记。</span><span class="sxs-lookup"><span data-stu-id="4492c-109">Retrieve an account token for a particular user by making a call to the unmanaged **LogonUser** method.</span></span> <span data-ttu-id="4492c-110">此方法不在 .NET Framework 基类库中，但在非托管 **advapi32.dll** 中。</span><span class="sxs-lookup"><span data-stu-id="4492c-110">This method is not in the .NET Framework base class library, but is located in the unmanaged **advapi32.dll**.</span></span> <span data-ttu-id="4492c-111">访问非托管代码中的方法是一项高级的操作，不在本文的讨论范围之内。</span><span class="sxs-lookup"><span data-stu-id="4492c-111">Accessing methods in unmanaged code is an advanced operation and is beyond the scope of this discussion.</span></span> <span data-ttu-id="4492c-112">有关详细信息，请参阅[与非托管代码交互操作](../../../docs/framework/interop/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4492c-112">For more information, see [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="4492c-113">有关 **LogonUser** 方法和 **advapi32.dll** 的详细信息，请参阅平台 SDK 文档。</span><span class="sxs-lookup"><span data-stu-id="4492c-113">For more information about the **LogonUser** method and **advapi32.dll**, see the Platform SDK documentation.</span></span>  
  
2.  <span data-ttu-id="4492c-114">创建 **WindowsIdentity** 类的新实例，并向其传递标记。</span><span class="sxs-lookup"><span data-stu-id="4492c-114">Create a new instance of the **WindowsIdentity** class, passing the token.</span></span> <span data-ttu-id="4492c-115">下面的代码演示此调用，其中 `hToken` 表示 Windows 标记。</span><span class="sxs-lookup"><span data-stu-id="4492c-115">The following code demonstrates this call, where `hToken` represents a Windows token.</span></span>  
  
    ```csharp  
    WindowsIdentity ImpersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim ImpersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3.  <span data-ttu-id="4492c-116">创建的新实例开始模拟<xref:System.Security.Principal.WindowsImpersonationContext>类并将其与初始化<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType>初始化类，如下面的代码中所示的方法。</span><span class="sxs-lookup"><span data-stu-id="4492c-116">Begin impersonation by creating a new instance of the <xref:System.Security.Principal.WindowsImpersonationContext> class and initializing it with the <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> method of the initialized class, as shown in the following code.</span></span>  
  
    ```csharp  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate()  
    ```  
  
4.  <span data-ttu-id="4492c-117">当不再需要进行模拟时，调用<xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType>方法还原模拟，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="4492c-117">When you no longer need to impersonate, call the <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> method to revert the impersonation, as shown in the following code.</span></span>  
  
    ```csharp  
    MyImpersonation.Undo();  
    ```  
  
    ```vb  
    MyImpersonation.Undo()  
    ```  
  
 <span data-ttu-id="4492c-118">如果受信任的代码具有已附加<xref:System.Security.Principal.WindowsPrincipal>对象传递给线程，您可以调用实例方法**Impersonate**，不采用帐户标记。</span><span class="sxs-lookup"><span data-stu-id="4492c-118">If trusted code has already attached a <xref:System.Security.Principal.WindowsPrincipal> object to the thread, you can call the instance method **Impersonate**, which does not take an account token.</span></span> <span data-ttu-id="4492c-119">请注意，仅当线程上的 **WindowsPrincipal** 对象所表示的用户不是当前正在执行进程的用户时，此操作才有用。</span><span class="sxs-lookup"><span data-stu-id="4492c-119">Note that this is only useful when the **WindowsPrincipal** object on the thread represents a user other than the one under which the process is currently executing.</span></span> <span data-ttu-id="4492c-120">例如，如果在使用 ASP.NET 时打开 Windows 身份验证并关闭模拟，则可能遇到此情形。</span><span class="sxs-lookup"><span data-stu-id="4492c-120">For example, you might encounter this situation using ASP.NET with Windows authentication turned on and impersonation turned off.</span></span> <span data-ttu-id="4492c-121">这时，进程在 Internet Information Services (IIS) 中配置的帐户下运行，而当前主体表示正在访问页面的 Windows 用户。</span><span class="sxs-lookup"><span data-stu-id="4492c-121">In this case, the process is running under an account configured in Internet Information Services (IIS) while the current principal represents the Windows user that is accessing the page.</span></span>  
  
 <span data-ttu-id="4492c-122">请注意，两者**Impersonate**也不**撤消**更改**主体**对象 (<xref:System.Security.Principal.IPrincipal>) 与当前调用上下文关联。</span><span class="sxs-lookup"><span data-stu-id="4492c-122">Note that neither **Impersonate** nor **Undo** changes the **Principal** object (<xref:System.Security.Principal.IPrincipal>)  associated with the current call context.</span></span> <span data-ttu-id="4492c-123">相反，模拟和还原会更改与当前操作系统进程关联的标记。</span><span class="sxs-lookup"><span data-stu-id="4492c-123">Rather, impersonation and reverting change the token associated with the current operating system process..</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4492c-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="4492c-124">See also</span></span>

- <xref:System.Security.Principal.WindowsIdentity>  
- <xref:System.Security.Principal.WindowsImpersonationContext>  
- [<span data-ttu-id="4492c-125">主体和标识对象</span><span class="sxs-lookup"><span data-stu-id="4492c-125">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)  
- [<span data-ttu-id="4492c-126">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="4492c-126">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)
