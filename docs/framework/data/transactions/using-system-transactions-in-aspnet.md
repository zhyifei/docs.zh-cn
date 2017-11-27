---
title: "在 ASP.NET 中使用 System.Transactions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6a27428211fad8c5c53f2799ee832baa6c644f36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-systemtransactions-in-aspnet"></a><span data-ttu-id="35e11-102">在 ASP.NET 中使用 System.Transactions</span><span class="sxs-lookup"><span data-stu-id="35e11-102">Using System.Transactions in ASP.NET</span></span>
<span data-ttu-id="35e11-103">本主题介绍如何才能在 <xref:System.Transactions> 应用程序中成功使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="35e11-103">This topic describes how you can successfully use <xref:System.Transactions> inside an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a><span data-ttu-id="35e11-104">在 ASP.NET 中启用 DistributedTransactionPermission</span><span class="sxs-lookup"><span data-stu-id="35e11-104">Enable DistributedTransactionPermission in ASP.NET</span></span>  
 <span data-ttu-id="35e11-105"><xref:System.Transactions> 支持部分受信任的调用方，可以用 **AllowPartiallyTrustedCallers** 特性 (APTCA) 对该对象进行标记。</span><span class="sxs-lookup"><span data-stu-id="35e11-105"><xref:System.Transactions> supports partially trusted callers and is marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="35e11-106">定义 <xref:System.Transactions> 的信任级别的根据是 <xref:System.Transactions> 所公开的资源类型（例如，系统内存、共享进程范围的资源、系统范围的资源以及其他资源）以及访问这些资源所需的信任级别。</span><span class="sxs-lookup"><span data-stu-id="35e11-106">The trust levels for <xref:System.Transactions> are defined based on the types of resources, (for example, system memory, shared process-wide resources, system-wide resources, and other resources), that <xref:System.Transactions> exposes and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="35e11-107">在部分信任环境中，除非向非完全信任程序集授予 <xref:System.Transactions.DistributedTransactionPermission>，否则该程序集只能在应用程序域中使用事务（在这种情况下，只有系统内存才是受保护的资源）。</span><span class="sxs-lookup"><span data-stu-id="35e11-107">In a partial-trust environment, a non-full trust assembly can only use transactions within the Application Domain (in this case, the only resource being protected is system memory), unless it is granted the <xref:System.Transactions.DistributedTransactionPermission>.</span></span>  
  
 <span data-ttu-id="35e11-108">每当将事务管理升级为由 Microsoft 分布式事务协调器 (MSDTC) 进行管理时，都会要求<xref:System.Transactions.DistributedTransactionPermission> 。</span><span class="sxs-lookup"><span data-stu-id="35e11-108"><xref:System.Transactions.DistributedTransactionPermission> is demanded whenever transaction management is escalated to be managed by the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="35e11-109">这种方案使用的是进程范围的资源尤其是全局资源，全局资源是指 MSDTC 日志中的保留空间。</span><span class="sxs-lookup"><span data-stu-id="35e11-109">This kind of scenario utilizes process-wide resources and particularly a global resource, which is the reserved space in the MSDTC log.</span></span> <span data-ttu-id="35e11-110">此用法的一个示例就是数据库或应用程序的 Web 前端，它使用数据库作为所提供服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="35e11-110">An example of this usage is a Web front-end to a database or an application that uses a database as part of the services it provides.</span></span>  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="35e11-111"> 有自己的一组信任级别，并可通过策略文件将特定的权限集与这些信任级别关联。</span><span class="sxs-lookup"><span data-stu-id="35e11-111"> has its own set of trust levels and associates a specific set of permissions with these trust levels through policy files.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="35e11-112">[ASP.NET 信任级别和策略文件](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)。</span><span class="sxs-lookup"><span data-stu-id="35e11-112"> [ASP.NET Trust Levels and Policy Files](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1).</span></span> <span data-ttu-id="35e11-113">在最初安装 Windows SDK 时，任何默认 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 策略文件都不与 <xref:System.Transactions.DistributedTransactionPermission>关联。</span><span class="sxs-lookup"><span data-stu-id="35e11-113">When you initially install the Windows SDK, none of the default [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] policy files are associated with the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="35e11-114">因此，当 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序中的事务升级为由 MSDTC 管理时，升级就会失败，并引发有关要求 <xref:System.Security.SecurityException> 的 <xref:System.Transactions.DistributedTransactionPermission>异常。</span><span class="sxs-lookup"><span data-stu-id="35e11-114">As such, when your transaction in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application is escalated to be managed by the MSDTC, the escalation fails with a <xref:System.Security.SecurityException> upon demanding the <xref:System.Transactions.DistributedTransactionPermission>.</span></span> <span data-ttu-id="35e11-115">若要在 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 部分信任环境中启用事务升级，应该用与 <xref:System.Transactions.DistributedTransactionPermission> 相同的默认信任级别授予 <xref:System.Data.SqlClient.SqlClientPermission>。</span><span class="sxs-lookup"><span data-stu-id="35e11-115">To enable transaction escalation in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] partial trust environment, you should grant the <xref:System.Transactions.DistributedTransactionPermission> in the same default trust levels as those of <xref:System.Data.SqlClient.SqlClientPermission>.</span></span> <span data-ttu-id="35e11-116">你可以配置自己的自定义信任级别和策略文件来支持这一方法，也可以修改默认策略文件（即 **Web_hightrust.config** 和 **Web_mediumtrust.config**）。</span><span class="sxs-lookup"><span data-stu-id="35e11-116">You can either configure your own custom trust level and policy file to support this, or you can modify the default policy files, which are **Web_hightrust.config** and **Web_mediumtrust.config**.</span></span>  
  
 <span data-ttu-id="35e11-117">若要修改策略文件，请添加**SecurityClass**元素**DistributedTransactionPermission**到**SecurityClasses**元素下的**PolicyLevel**元素和添加相应**IPermission**元素下的[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** system.transactions。</span><span class="sxs-lookup"><span data-stu-id="35e11-117">To modify the policy files, add a **SecurityClass** element for **DistributedTransactionPermission** to the **SecurityClasses** element under the **PolicyLevel** element and add a corresponding **IPermission** element under the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** for System.Transactions.</span></span> <span data-ttu-id="35e11-118">下面的配置文件演示了这一点。</span><span class="sxs-lookup"><span data-stu-id="35e11-118">The following configuration file demonstrates this.</span></span>  
  
```xml  
<SecurityClasses>  
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
...  
</SecurityClasses>  
  
<PermissionSet  
  class="NamedPermissionSet"  
  version="1"  
  Name="ASP.Net">  
     <IPermission  
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
        version="1"  
        Unrestricted="true"  
     />  
...  
</PermissionSet>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="35e11-119"> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 安全策略，请参阅 [securityPolicy 元素（ASP.NET 设置架构）](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba)，否则该程序集只能在应用程序域中使用事务（在这种情况下，只有系统内存才是受保护的资源）。</span><span class="sxs-lookup"><span data-stu-id="35e11-119"> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] security policy, see [securityPolicy Element (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba).</span></span>  
  
## <a name="dynamic-compilation"></a><span data-ttu-id="35e11-120">动态编译</span><span class="sxs-lookup"><span data-stu-id="35e11-120">Dynamic Compilation</span></span>  
 <span data-ttu-id="35e11-121">如果要在访问时动态编译的 <xref:System.Transactions> 应用程序中导入和使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ，则应将对该 <xref:System.Transactions> 程序集的引用放入配置文件中。</span><span class="sxs-lookup"><span data-stu-id="35e11-121">If you want to import and use <xref:System.Transactions> in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is dynamically compiled on access, you should place a reference to the <xref:System.Transactions> assembly in the configuration file.</span></span> <span data-ttu-id="35e11-122">具体来说，应将该引用添加到默认根 **Web.config**/**compilation** / **assemblies** 节之下。</span><span class="sxs-lookup"><span data-stu-id="35e11-122">Specifically, the reference should be added under the **compilation**/**assemblies** section of the default root **Web.config** configuration file, or a specific Web application's configuration file.</span></span> <span data-ttu-id="35e11-123">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="35e11-123">The following example demonstrates this.</span></span>  
  
```xml  
<configuration>  
   <system.web>  
      <compilation>  
         <assemblies>  
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
         </assemblies>  
      </compilation>  
   </system.web>  
</configuration>  
```  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="35e11-124"> [compilation 的 assemblies 的 add 元素（ASP.NET 设置架构）](http://msdn.microsoft.com/en-us/602197e8-108d-4249-b752-ba2a318f75e4)，否则该程序集只能在应用程序域中使用事务（在这种情况下，只有系统内存才是受保护的资源）。</span><span class="sxs-lookup"><span data-stu-id="35e11-124"> [add Element for assemblies for compilation (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/602197e8-108d-4249-b752-ba2a318f75e4).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e11-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35e11-125">See Also</span></span>  
 [<span data-ttu-id="35e11-126">ASP.NET 信任级别和策略文件</span><span class="sxs-lookup"><span data-stu-id="35e11-126">ASP.NET Trust Levels and Policy Files</span></span>](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)  
 [<span data-ttu-id="35e11-127">securityPolicy 元素 （ASP.NET 设置架构）</span><span class="sxs-lookup"><span data-stu-id="35e11-127">securityPolicy Element (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/en-us/469d8d22-d263-46bb-8400-40d8d027faba)  
 [<span data-ttu-id="35e11-128">事务管理升级</span><span class="sxs-lookup"><span data-stu-id="35e11-128">Transaction Management Escalation</span></span>](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
