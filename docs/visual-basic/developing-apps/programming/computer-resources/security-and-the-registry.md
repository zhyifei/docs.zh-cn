---
title: 安全性与注册表 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- security [Visual Basic], registry
- registry [Visual Basic], security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
ms.openlocfilehash: dc0071d1fddf99bd712ebe8aea5c61bbc3522f93
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839348"
---
# <a name="security-and-the-registry-visual-basic"></a><span data-ttu-id="c946a-102">安全性与注册表 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c946a-102">Security and the Registry (Visual Basic)</span></span>
<span data-ttu-id="c946a-103">本页讨论将数据存储在注册表中的安全意义。</span><span class="sxs-lookup"><span data-stu-id="c946a-103">This page discusses the security implications of storing data in the registry.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="c946a-104">权限</span><span class="sxs-lookup"><span data-stu-id="c946a-104">Permissions</span></span>  
 <span data-ttu-id="c946a-105">即使注册表项受 ACL（访问控制列表）保护，在注册表中以纯文本形式存储机密信息（例如密码）也不安全。</span><span class="sxs-lookup"><span data-stu-id="c946a-105">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (access control lists).</span></span>  
  
 <span data-ttu-id="c946a-106">对注册表进行操作时，如果允许对系统资源或受保护的信息进行不适当的访问，则可能会降低安全性。</span><span class="sxs-lookup"><span data-stu-id="c946a-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span> <span data-ttu-id="c946a-107">若要使用这些属性，必须具有来自 <xref:System.Security.Permissions.RegistryPermissionAccess> 枚举（其控制对注册表变量的访问）的读取和写入权限。</span><span class="sxs-lookup"><span data-stu-id="c946a-107">To use these properties, you must have read and write permissions from the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration, which controls access to registry variables.</span></span> <span data-ttu-id="c946a-108">通过完全信任运行的任何代码（在默认安全策略下，指安装在用户本地硬盘上的任何代码）都具有访问注册表的必要权限。</span><span class="sxs-lookup"><span data-stu-id="c946a-108">Any code running with full trust (under the default security policy, this is any code installed on the user's local hard disk) has the necessary permissions to access the registry.</span></span> <span data-ttu-id="c946a-109">有关详细信息，请参阅 <xref:System.Security.Permissions.RegistryPermission> 类。</span><span class="sxs-lookup"><span data-stu-id="c946a-109">For more information, see <xref:System.Security.Permissions.RegistryPermission> class.</span></span>  
  
 <span data-ttu-id="c946a-110">不应将注册表变量存储在某些内存位置，在这些位置，不具有 <xref:System.Security.Permissions.RegistryPermission> 的代码可访问这些变量。</span><span class="sxs-lookup"><span data-stu-id="c946a-110">Registry variables should not be stored in memory locations where code without <xref:System.Security.Permissions.RegistryPermission> can access them.</span></span> <span data-ttu-id="c946a-111">同样，授予权限时，授予顺利完成操作所需的最小特权。</span><span class="sxs-lookup"><span data-stu-id="c946a-111">Similarly, when granting permissions, grant the minimum privileges necessary to get the job done.</span></span>  
  
 <span data-ttu-id="c946a-112">通过 <xref:System.Security.Permissions.RegistryPermissionAccess> 枚举定义注册表权限访问值。</span><span class="sxs-lookup"><span data-stu-id="c946a-112">Registry permission access values are defined by the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration.</span></span> <span data-ttu-id="c946a-113">下表详细说明了其成员。</span><span class="sxs-lookup"><span data-stu-id="c946a-113">The following table details its members.</span></span>  
  
|<span data-ttu-id="c946a-114">值</span><span class="sxs-lookup"><span data-stu-id="c946a-114">Value</span></span>|<span data-ttu-id="c946a-115">对注册表变量的访问</span><span class="sxs-lookup"><span data-stu-id="c946a-115">Access to Registry Variables</span></span>|  
|-----------|----------------------------------|  
|`AllAccess`|<span data-ttu-id="c946a-116">创建、读取和写入</span><span class="sxs-lookup"><span data-stu-id="c946a-116">Create, read, and write</span></span>|  
|`Create`|<span data-ttu-id="c946a-117">创建</span><span class="sxs-lookup"><span data-stu-id="c946a-117">Create</span></span>|  
|`NoAccess`|<span data-ttu-id="c946a-118">无访问权限</span><span class="sxs-lookup"><span data-stu-id="c946a-118">No access</span></span>|  
|`Read`|<span data-ttu-id="c946a-119">读取</span><span class="sxs-lookup"><span data-stu-id="c946a-119">Read</span></span>|  
|`Write`|<span data-ttu-id="c946a-120">Write</span><span class="sxs-lookup"><span data-stu-id="c946a-120">Write</span></span>|  
  
## <a name="checking-values-in-registry-keys"></a><span data-ttu-id="c946a-121">检查注册表项中的值</span><span class="sxs-lookup"><span data-stu-id="c946a-121">Checking Values in Registry Keys</span></span>  
 <span data-ttu-id="c946a-122">创建注册表值时，需要确定该值已存在时应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c946a-122">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="c946a-123">另一进程（可能是恶意进程）可能已创建了该值，并拥有对该值的访问权。</span><span class="sxs-lookup"><span data-stu-id="c946a-123">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="c946a-124">将数据放入注册表值后，其他进程即可使用这些数据。</span><span class="sxs-lookup"><span data-stu-id="c946a-124">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="c946a-125">若要防止出现这种情况，请使用 `GetValue` 方法。</span><span class="sxs-lookup"><span data-stu-id="c946a-125">To prevent this, use the `GetValue` method.</span></span> <span data-ttu-id="c946a-126">如果项不存在，则该方法返回 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="c946a-126">It returns `Nothing` if the key does not already exist.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c946a-127">从 Web 应用程序读取注册表时，当前用户的标识依赖于在 Web 应用程序中实现的身份验证和模拟。</span><span class="sxs-lookup"><span data-stu-id="c946a-127">When reading the registry from a Web application, the identity of current user depends on the authentication and impersonation implemented in the Web application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c946a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c946a-128">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [<span data-ttu-id="c946a-129">读取和写入注册表</span><span class="sxs-lookup"><span data-stu-id="c946a-129">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
