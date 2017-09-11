---
title: "如何：在 Visual Basic 中从注册表项中读取值"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- registry keys, determining if a value exists in
- My.Computer.Registry object, examples
- registry, determining if values exist
- registry keys, reading from
- registry, reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 69b833777629cfd642ab75ac055b96b59c1da70b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a><span data-ttu-id="8cbc0-102">如何：在 Visual Basic 中从注册表项中读取值</span><span class="sxs-lookup"><span data-stu-id="8cbc0-102">How to: Read a Value from a Registry Key in Visual Basic</span></span>
<span data-ttu-id="8cbc0-103">`My.Computer.Registry` 对象的 `GetValue` 方法可以用于读取 Windows 注册表中的值。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-103">The `GetValue` method of the `My.Computer.Registry` object can be used to read values in the Windows registry.</span></span>  
  
 <span data-ttu-id="8cbc0-104">如果在下面的示例中，“Software\MyApp”项不存在，则引发异常。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-104">If the key, "Software\MyApp" in the following example, does not exist, an exception is thrown.</span></span> <span data-ttu-id="8cbc0-105">如果在下面的示例中，`ValueName`“Name”不存在，则返回 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-105">If the `ValueName`,  "Name" in the following example, does not exist, `Nothing` is returned.</span></span>  
  
 <span data-ttu-id="8cbc0-106">`GetValue` 方法还可以用于确定特定注册表项中是否存在给定值。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-106">The `GetValue` method can also be used to determine whether a given value exists in a specific registry key.</span></span>  
  
 <span data-ttu-id="8cbc0-107">代码从 Web 应用程序读取注册表时，当前用户取决于在 Web 应用程序中实现的身份验证和模拟。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-107">When code reads the registry from a Web application, the current user is determined by the authentication and impersonation that is implemented in the Web application.</span></span>  
  
### <a name="to-read-a-value-from-a-registry-key"></a><span data-ttu-id="8cbc0-108">从注册表项读取值</span><span class="sxs-lookup"><span data-stu-id="8cbc0-108">To read a value from a registry key</span></span>  
  
-   <span data-ttu-id="8cbc0-109">使用 `GetValue` 方法（指定路径和名称）可从注册表项读取值。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-109">Use the `GetValue` method, specifying the path and name) to read a value from registry key.</span></span> <span data-ttu-id="8cbc0-110">下面的示例从 `HKEY_CURRENT_USER\Software\MyApp` 读取值 `Name` 并将它显示在消息框中。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-110">The following example reads the value `Name` from `HKEY_CURRENT_USER\Software\MyApp` and displays it in a message box.</span></span>  
  
     <span data-ttu-id="8cbc0-111">[!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8cbc0-111">[!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]</span></span>  
  
 <span data-ttu-id="8cbc0-112">此代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-112">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="8cbc0-113">在代码片段选取器中，它位于“Windows 操作系统”>“注册表”中。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-113">In the code snippet picker, it is located in **Windows Operating System > Registry**.</span></span> <span data-ttu-id="8cbc0-114">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-114">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a><span data-ttu-id="8cbc0-115">确定值是否存在于注册表项中</span><span class="sxs-lookup"><span data-stu-id="8cbc0-115">To determine whether a value exists in a registry key</span></span>  
  
-   <span data-ttu-id="8cbc0-116">使用 `GetValue` 方法可检索值。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-116">Use the `GetValue` method to retrieve the value.</span></span> <span data-ttu-id="8cbc0-117">下面的代码检查值是否存在并在它不存在时返回消息。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-117">The following code checks whether the value exists and returns a message if it does not.</span></span>  
  
     <span data-ttu-id="8cbc0-118">[!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8cbc0-118">[!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8cbc0-119">可靠编程</span><span class="sxs-lookup"><span data-stu-id="8cbc0-119">Robust Programming</span></span>  
 <span data-ttu-id="8cbc0-120">注册表包含用于存储数据的顶层（或根）项。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-120">The registry holds top-level, or root, keys that are used to store data.</span></span> <span data-ttu-id="8cbc0-121">例如，HKEY_LOCAL_MACHINE 根项用于存储所有用户使用的计算机级别设置，而 HKEY_CURRENT_USER 用于存储特定于单个用户的数据。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-121">For instance, the HKEY_LOCAL_MACHINE root key is used for storing machine-level settings used by all users, while HKEY_CURRENT_USER is used for storing data specific to an individual user.</span></span>  
  
 <span data-ttu-id="8cbc0-122">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="8cbc0-122">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8cbc0-123">密钥名称是 `Nothing` (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-123">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="8cbc0-124">用户没有从注册表项 (<xref:System.Security.SecurityException>) 进行读取的权限。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-124">The user does not have permissions to read from registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="8cbc0-125">项名称超过 255 个字符的限制 (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-125">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8cbc0-126">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="8cbc0-126">.NET Framework Security</span></span>  
 <span data-ttu-id="8cbc0-127">若要运行此进程，程序集需要 <xref:System.Security.Permissions.RegistryPermission> 类授予的特权等级。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-127">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="8cbc0-128">如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-128">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="8cbc0-129">同样，用户必须具有用于创建或写入设置的正确 ACL。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-129">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="8cbc0-130">例如，具有代码访问安全性权限的本地应用程序可能没有操作系统权限。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-130">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="8cbc0-131">有关详细信息，请参阅[代码访问安全性基础知识](https://msdn.microsoft.com/library/33tceax8)。</span><span class="sxs-lookup"><span data-stu-id="8cbc0-131">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cbc0-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cbc0-132">See Also</span></span>  
 <span data-ttu-id="8cbc0-133"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span><span class="sxs-lookup"><span data-stu-id="8cbc0-133"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span></span>   
 <span data-ttu-id="8cbc0-134"><xref:Microsoft.Win32.RegistryHive></span><span class="sxs-lookup"><span data-stu-id="8cbc0-134"><xref:Microsoft.Win32.RegistryHive></span></span>   
 [<span data-ttu-id="8cbc0-135">读取和写入注册表</span><span class="sxs-lookup"><span data-stu-id="8cbc0-135">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)

