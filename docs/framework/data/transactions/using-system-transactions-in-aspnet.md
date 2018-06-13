---
title: 在 ASP.NET 中使用 System.Transactions
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 142f5e18682b02dfb659959a19b79c10fb3110c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364747"
---
# <a name="using-systemtransactions-in-aspnet"></a>在 ASP.NET 中使用 System.Transactions
本主题介绍如何才能在 <xref:System.Transactions> 应用程序中成功使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 。  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a>在 ASP.NET 中启用 DistributedTransactionPermission  
 <xref:System.Transactions> 支持部分受信任的调用方，可以用 **AllowPartiallyTrustedCallers** 特性 (APTCA) 对该对象进行标记。 定义 <xref:System.Transactions> 的信任级别的根据是 <xref:System.Transactions> 所公开的资源类型（例如，系统内存、共享进程范围的资源、系统范围的资源以及其他资源）以及访问这些资源所需的信任级别。 在部分信任环境中，除非向非完全信任程序集授予 <xref:System.Transactions.DistributedTransactionPermission>，否则该程序集只能在应用程序域中使用事务（在这种情况下，只有系统内存才是受保护的资源）。  
  
 每当将事务管理升级为由 Microsoft 分布式事务协调器 (MSDTC) 进行管理时，都会要求<xref:System.Transactions.DistributedTransactionPermission> 。 这种方案使用的是进程范围的资源尤其是全局资源，全局资源是指 MSDTC 日志中的保留空间。 此用法的一个示例就是数据库或应用程序的 Web 前端，它使用数据库作为所提供服务的一部分。  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 有自己的一组信任级别，并可通过策略文件将特定的权限集与这些信任级别关联。 有关详细信息，请参阅[ASP.NET 信任级别和策略文件](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)。 在最初安装 Windows SDK 时，任何默认 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 策略文件都不与 <xref:System.Transactions.DistributedTransactionPermission>关联。 因此，当 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序中的事务升级为由 MSDTC 管理时，升级就会失败，并引发有关要求 <xref:System.Security.SecurityException> 的 <xref:System.Transactions.DistributedTransactionPermission>异常。 若要在 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 部分信任环境中启用事务升级，应该用与 <xref:System.Transactions.DistributedTransactionPermission> 相同的默认信任级别授予 <xref:System.Data.SqlClient.SqlClientPermission>。 你可以配置自己的自定义信任级别和策略文件来支持这一方法，也可以修改默认策略文件（即 **Web_hightrust.config** 和 **Web_mediumtrust.config**）。  
  
 若要修改策略文件，请添加**SecurityClass**元素**DistributedTransactionPermission**到**SecurityClasses**元素下的**PolicyLevel**元素和添加相应**IPermission**元素下的[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** system.transactions。 下面的配置文件演示了这一点。  
  
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
  
 有关详细信息[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]安全策略，请参阅[securityPolicy 元素 （ASP.NET 设置架构）](http://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba)。  
  
## <a name="dynamic-compilation"></a>动态编译  
 如果要在访问时动态编译的 <xref:System.Transactions> 应用程序中导入和使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ，则应将对该 <xref:System.Transactions> 程序集的引用放入配置文件中。 具体来说，应将该引用添加到默认根 **Web.config**/**compilation** / **assemblies** 节之下。 下面的示例演示这一操作。  
  
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
  
 有关详细信息，请参阅[编译 （ASP.NET 设置架构） 的程序集添加元素](http://msdn.microsoft.com/library/602197e8-108d-4249-b752-ba2a318f75e4)。  
  
## <a name="see-also"></a>请参阅  
 [ASP.NET 信任级别和策略文件](http://msdn.microsoft.com/library/f897c794-10d3-414c-86b7-59b66564bbf1)  
 [securityPolicy 元素 （ASP.NET 设置架构）](http://msdn.microsoft.com/library/469d8d22-d263-46bb-8400-40d8d027faba)  
 [事务管理升级](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
