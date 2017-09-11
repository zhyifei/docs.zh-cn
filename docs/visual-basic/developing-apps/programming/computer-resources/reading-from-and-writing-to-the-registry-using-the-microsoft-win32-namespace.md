---
title: "使用 Microsoft.Win32 命名空间读取和写入注册表 (Visual Basic)"
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
- registry, Visual Basic
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cefde5317b2ed2bc0a2834224b1475e8020f7f25
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a><span data-ttu-id="631af-102">使用 Microsoft.Win32 命名空间读取和写入注册表 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="631af-102">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace (Visual Basic)</span></span>
<span data-ttu-id="631af-103">虽然在针对注册表进行编程时，`My.Computer.Registry` 应涵盖你的基本需求，不过你还可以使用 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 的 <xref:Microsoft.Win32> 命名空间中的 <xref:Microsoft.Win32.Registry> 和 <xref:Microsoft.Win32.RegistryKey> 类。</span><span class="sxs-lookup"><span data-stu-id="631af-103">Although `My.Computer.Registry` should cover your basic needs when programming against the registry, you can also use the <xref:Microsoft.Win32.Registry> and <xref:Microsoft.Win32.RegistryKey> classes in the <xref:Microsoft.Win32> namespace of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="keys-in-the-registry-class"></a><span data-ttu-id="631af-104">注册表类中的项</span><span class="sxs-lookup"><span data-stu-id="631af-104">Keys in the Registry Class</span></span>  
 <span data-ttu-id="631af-105"><xref:Microsoft.Win32.Registry> 类提供可以用于访问子项及其值的注册表基项。</span><span class="sxs-lookup"><span data-stu-id="631af-105">The <xref:Microsoft.Win32.Registry> class supplies the base registry keys that can be used to access subkeys and their values.</span></span> <span data-ttu-id="631af-106">这些基项本身是只读的。</span><span class="sxs-lookup"><span data-stu-id="631af-106">The base keys themselves are read-only.</span></span> <span data-ttu-id="631af-107">下表列出并介绍了 <xref:Microsoft.Win32.Registry> 类公开的七个项。</span><span class="sxs-lookup"><span data-stu-id="631af-107">The following table lists and describes the seven keys exposed by the <xref:Microsoft.Win32.Registry> class.</span></span>  
  
|<span data-ttu-id="631af-108">**Key**</span><span class="sxs-lookup"><span data-stu-id="631af-108">**Key**</span></span>|<span data-ttu-id="631af-109">**描述**</span><span class="sxs-lookup"><span data-stu-id="631af-109">**Description**</span></span>|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|<span data-ttu-id="631af-110">定义文档的类型以及与这些类型关联的属性。</span><span class="sxs-lookup"><span data-stu-id="631af-110">Defines the types of documents and the properties associated with those types.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|<span data-ttu-id="631af-111">包含不是特定于用户的硬件配置信息。</span><span class="sxs-lookup"><span data-stu-id="631af-111">Contains hardware configuration information that is not user-specific.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|<span data-ttu-id="631af-112">包含有关当前用户首选项的信息，如环境变量。</span><span class="sxs-lookup"><span data-stu-id="631af-112">Contains information about the current user preferences, such as environmental variables.</span></span>|  
|<xref:Microsoft.Win32.Registry.DynData>|<span data-ttu-id="631af-113">包含动态注册表数据，如虚拟设备驱动程序使用的数据。</span><span class="sxs-lookup"><span data-stu-id="631af-113">Contains dynamic registry data, such as that used by Virtual Device Drivers.</span></span>|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|<span data-ttu-id="631af-114">包含保存本地计算机的配置数据的五个子项（硬件、SAM、安全性、软件和系统）。</span><span class="sxs-lookup"><span data-stu-id="631af-114">Contains five subkeys (Hardware, SAM, Security, Software, and System) that hold the configuration data for the local computer.</span></span>|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|<span data-ttu-id="631af-115">包含软件组件的性能信息。</span><span class="sxs-lookup"><span data-stu-id="631af-115">Contains performance information for software components.</span></span>|  
|<xref:Microsoft.Win32.Registry.Users>|<span data-ttu-id="631af-116">包含有关默认用户首选项的信息。</span><span class="sxs-lookup"><span data-stu-id="631af-116">Contains information about the default user preferences.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="631af-117">将数据写入当前用户 (<xref:Microsoft.Win32.Registry.CurrentUser>) 比写入本地计算机 (<xref:Microsoft.Win32.Registry.LocalMachine>) 更安全。</span><span class="sxs-lookup"><span data-stu-id="631af-117">It is more secure to write data to the current user (<xref:Microsoft.Win32.Registry.CurrentUser>) than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span> <span data-ttu-id="631af-118">当你创建的项以前已由其他进程（可能是恶意的）进行了创建时，会发生通常称为“强占”的情况。</span><span class="sxs-lookup"><span data-stu-id="631af-118">A condition that's typically referred to as "squatting" occurs when the key you are creating was previously created by another, possibly malicious, process.</span></span> <span data-ttu-id="631af-119">若要防止此情况发生，请使用在项尚未存在时返回 `Nothing` 的方法（如 <xref:Microsoft.Win32.RegistryKey.GetValue%2A>）。</span><span class="sxs-lookup"><span data-stu-id="631af-119">To prevent this from occurring, use a method, such as <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, that returns `Nothing` if the key does not already exist.</span></span>  
  
## <a name="reading-a-value-from-the-registry"></a><span data-ttu-id="631af-120">从注册表中读取值</span><span class="sxs-lookup"><span data-stu-id="631af-120">Reading a Value from the Registry</span></span>  
 <span data-ttu-id="631af-121">下面的代码演示如何从 HKEY_CURRENT_USER 中读取字符串。</span><span class="sxs-lookup"><span data-stu-id="631af-121">The following code shows how to read a string from HKEY_CURRENT_USER.</span></span>  
  
 <span data-ttu-id="631af-122">[!code-vb[VbResourceTasks#20](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="631af-122">[!code-vb[VbResourceTasks#20](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_1.vb)]</span></span>  
  
 <span data-ttu-id="631af-123">下面的代码读取一个字符串，使它递增，然后将它写入 HKEY_CURRENT_USER。</span><span class="sxs-lookup"><span data-stu-id="631af-123">The following code reads, increments, and then writes a string to HKEY_CURRENT_USER.</span></span>  
  
 <span data-ttu-id="631af-124">[!code-vb[VbResourceTasks#21](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="631af-124">[!code-vb[VbResourceTasks#21](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="631af-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="631af-125">See Also</span></span>  
 <span data-ttu-id="631af-126"><xref:System.SystemException></span><span class="sxs-lookup"><span data-stu-id="631af-126"><xref:System.SystemException></span></span>   
 <span data-ttu-id="631af-127"><xref:System.ApplicationException></span><span class="sxs-lookup"><span data-stu-id="631af-127"><xref:System.ApplicationException></span></span>   
 <span data-ttu-id="631af-128"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span><span class="sxs-lookup"><span data-stu-id="631af-128"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span></span>   
 <span data-ttu-id="631af-129">[Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span><span class="sxs-lookup"><span data-stu-id="631af-129">[Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span></span>  
 <span data-ttu-id="631af-130">[读取和写入注册表](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="631af-130">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
 [<span data-ttu-id="631af-131">安全性与注册表</span><span class="sxs-lookup"><span data-stu-id="631af-131">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)

