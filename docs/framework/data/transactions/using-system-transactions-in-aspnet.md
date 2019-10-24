---
title: 在 ASP.NET 中使用 System.Transactions
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: 6f88a4b06a9a83cf920601b7abe887d8b5fa7839
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774146"
---
# <a name="using-systemtransactions-in-aspnet"></a>在 ASP.NET 中使用 System.Transactions
本主题描述如何才能在 ASP.NET 应用程序中成功使用 <xref:System.Transactions>。

## <a name="enable-distributedtransactionpermission-in-aspnet"></a>在 ASP.NET 中启用 DistributedTransactionPermission
 <xref:System.Transactions> 支持部分受信任的调用方，可以用 **AllowPartiallyTrustedCallers** 特性 (APTCA) 对该对象进行标记。 @No__t_0 的信任级别是根据资源类型（例如，系统内存、共享进程范围的资源、系统范围的资源以及其他资源）定义的，这些资源是 <xref:System.Transactions> 公开的，以及访问这些资源所需的信任级别。中心. 在部分信任环境中，除非向非完全信任程序集授予 <xref:System.Transactions.DistributedTransactionPermission>，否则该程序集只能在应用程序域中使用事务（在这种情况下，只有系统内存才是受保护的资源）。

 每当将事务管理升级为由 Microsoft 分布式事务协调器 (MSDTC) 进行管理时，都会要求<xref:System.Transactions.DistributedTransactionPermission> 。 这种方案使用的是进程范围的资源尤其是全局资源，全局资源是指 MSDTC 日志中的保留空间。 此用法的一个示例就是数据库或应用程序的 Web 前端，它使用数据库作为所提供服务的一部分。

 ASP.NET 有自己的一组信任级别，并可通过策略文件将特定的权限集与这些信任级别关联。 有关详细信息，请参阅[ASP.NET 信任级别和策略文件](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))。 最初安装 Windows SDK 时，任何默认 ASP.NET 策略文件都不与 <xref:System.Transactions.DistributedTransactionPermission> 相关联。 因此，当 ASP.NET 应用程序中的事务升级为由 MSDTC 管理时，升级就会失败，并引发有关要求 <xref:System.Security.SecurityException> 的 <xref:System.Transactions.DistributedTransactionPermission> 异常。 若要在 ASP.NET 部分信任环境中启用事务升级，应该用与 <xref:System.Transactions.DistributedTransactionPermission> 相同的默认信任级别授予 <xref:System.Data.SqlClient.SqlClientPermission>。 你可以配置自己的自定义信任级别和策略文件来支持这一方法，也可以修改默认策略文件（即 **Web_hightrust.config** 和 **Web_mediumtrust.config**）。

 若要修改策略文件，请将**DistributedTransactionPermission**的**SecurityClass**元素添加到**PolicyLevel**元素下的**SecurityClasses**元素，并在ASP.NET **vstecasp** 。 下面的配置文件演示了这一点。

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

 有关 ASP.NET 安全策略的详细信息，请参阅[Ws-securitypolicy 元素（ASP.NET Settings Schema）](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))。

## <a name="dynamic-compilation"></a>动态编译
 如果要在访问时动态编译的 ASP.NET 应用程序中导入和使用 <xref:System.Transactions>，则应将对该 <xref:System.Transactions> 程序集的引用放入配置文件中。 具体来说，应将该引用添加到默认根 **Web.config**/**compilation** / **assemblies** 节之下。 下面的示例演示这一操作。

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

 有关详细信息，请参阅为[编译程序集添加元素（ASP.NET 设置架构）](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100))。

## <a name="see-also"></a>请参阅

- [ASP.NET 信任级别和策略文件](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))
- [Ws-securitypolicy 元素（ASP.NET 设置架构）](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))
- [事务管理升级](transaction-management-escalation.md)
