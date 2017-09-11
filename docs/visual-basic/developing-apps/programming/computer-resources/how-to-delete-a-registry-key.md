---
title: "如何：在 Visual Basic 中删除注册表项"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.DeleteSetting
dev_langs:
- VB
helpviewer_keywords:
- GetSetting function
- registry, deleting values
- GetAllSettings function
- registry keys, deleting
- registry, deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
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
ms.openlocfilehash: 0fc37aff9f6a0ae3a7953377ebf95179d01bb693
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a><span data-ttu-id="476b2-102">如何：在 Visual Basic 中删除注册表项</span><span class="sxs-lookup"><span data-stu-id="476b2-102">How to: Delete a Registry Key in Visual Basic</span></span>
<span data-ttu-id="476b2-103"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> 和 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> 方法可以用于删除注册表项。</span><span class="sxs-lookup"><span data-stu-id="476b2-103">The <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> and <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> methods can be used to delete registry keys.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="476b2-104">过程</span><span class="sxs-lookup"><span data-stu-id="476b2-104">Procedure</span></span>  
  
#### <a name="to-delete-a-registry-key"></a><span data-ttu-id="476b2-105">删除注册表项</span><span class="sxs-lookup"><span data-stu-id="476b2-105">To delete a registry key</span></span>  
  
-   <span data-ttu-id="476b2-106">使用 `DeleteSubKey` 方法删除注册表项。</span><span class="sxs-lookup"><span data-stu-id="476b2-106">Use the `DeleteSubKey` method to delete a registry key.</span></span> <span data-ttu-id="476b2-107">此示例将删除 CurrentUser 配置单元中的软件/TestApp 项。</span><span class="sxs-lookup"><span data-stu-id="476b2-107">This example deletes the key Software/TestApp in the CurrentUser hive.</span></span> <span data-ttu-id="476b2-108">可在代码中更改为相应的字符串，或使它依赖于用户提供的信息。</span><span class="sxs-lookup"><span data-stu-id="476b2-108">You can change this in the code to the appropriate string, or have it rely on user-supplied information.</span></span>  
  
     <span data-ttu-id="476b2-109">[!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="476b2-109">[!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="476b2-110">可靠编程</span><span class="sxs-lookup"><span data-stu-id="476b2-110">Robust Programming</span></span>  
 <span data-ttu-id="476b2-111">如果键/值对不存在，`DeleteSubKey` 方法将返回一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="476b2-111">The `DeleteSubKey` method returns an empty string if the key/value pair does not exist.</span></span>  
  
 <span data-ttu-id="476b2-112">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="476b2-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="476b2-113">密钥名称是 `Nothing` (<xref:System.ArgumentNullException>)。</span><span class="sxs-lookup"><span data-stu-id="476b2-113">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="476b2-114">用户没有删除注册表项的权限 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="476b2-114">The user does not have permissions to delete registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="476b2-115">项名称超过 255 个字符的限制 (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="476b2-115">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="476b2-116">注册表项为只读 (<xref:System.UnauthorizedAccessException>)。</span><span class="sxs-lookup"><span data-stu-id="476b2-116">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="476b2-117">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="476b2-117">.NET Framework Security</span></span>  
 <span data-ttu-id="476b2-118">如果未授予足够的运行时权限 (<xref:System.Security.Permissions.RegistryPermission>) 或用户没有用于创建或写入设置的适当访问权限（由 ACL 确定），则注册表调用将失败。</span><span class="sxs-lookup"><span data-stu-id="476b2-118">Registry calls fail if either sufficient run-time permissions are not granted (<xref:System.Security.Permissions.RegistryPermission>) or if the user does not have the correct access (as determined by the ACLs) for creating or writing to settings.</span></span> <span data-ttu-id="476b2-119">例如，具有代码访问安全性权限的本地应用程序可能没有操作系统权限。</span><span class="sxs-lookup"><span data-stu-id="476b2-119">For example, a local application that has the code access security permission might not have operating system permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="476b2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="476b2-120">See Also</span></span>  
 <span data-ttu-id="476b2-121"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="476b2-121"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span></span>   
 <span data-ttu-id="476b2-122"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="476b2-122"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span></span>   
 <span data-ttu-id="476b2-123"><xref:Microsoft.Win32.RegistryKey></span><span class="sxs-lookup"><span data-stu-id="476b2-123"><xref:Microsoft.Win32.RegistryKey></span></span>   
 <span data-ttu-id="476b2-124">[安全性与注册表](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="476b2-124">[Security and the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md) </span></span>  
 [<span data-ttu-id="476b2-125">读取和写入注册表</span><span class="sxs-lookup"><span data-stu-id="476b2-125">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)

