---
title: ".NET Framework 4.5.2 中的运行时更改 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 94ac01ea-8b12-44d2-b12b-5220a5d14d87
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 247fbf574f13985fc941f252c0a6e7268194c079
ms.contentlocale: zh-cn
ms.lasthandoff: 05/22/2017

---
# <a name="runtime-changes-in-the-net-framework-452"></a>.NET Framework 4.5.2 中的运行时更改
在极少数情况下，运行时更改可能影响面向以前版本的 .NET Framework 但在 .NET Framework 4.5.2 运行时上运行的现有应用。 它们包括以下区域中的更改：  
  
-   [ASP.NET 2.0](#ASP_NET)  
  
-   [Entity Framework](#EF)  
  
<a name="ASP_NET"></a>   
## <a name="aspnet-runtime-changes"></a>ASP.NET 运行时更改  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|[页面元素](http://msdn.microsoft.com/en-us/4123bb66-3fe4-4d62-b70e-33758656b458)的 `enableViewStateMac` 特性|ASP.NET 不再允许开发人员指定：<br /><br /> `<pages enableViewStateMac="false" />`<br /><br /> 或：<br /><br /> `<@Page EnableViewStateMac="false" %>`|现在，针对所有带嵌入视图状态的请求强制执行视图状态消息身份验证代码 (MAC)。 仅影响将 <xref:System.Web.UI.Page.EnableViewStateMac%2A> 属性显式设置为 `false` 的应用。<br /><br /> 有关详细信息，请参阅[解决视图状态消息验证代码 (MAC) 错误](http://support.microsoft.com/kb/2915218)。|主要|  
  
<a name="EF"></a>   
## <a name="entity-framework-runtime-changes"></a>Entity Framework 运行时更改  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|QueryView 上的关系|当应用执行涉及到带有 0..1 导航属性（此属性尝试将相关实体包含为查询的一部分，例如，通过调用 <xref:System.StackOverflowException>）的查询时，Entity Framework 将不再引发 `.Include(e=>e.RelatedNavProp)` 异常。|在运行调用 `.Include` 的查询时，此更改仅影响使用带有 1-0..1 关系的 QueryViews 的代码。 它可以改善可靠性，并且应该几乎对所有应用透明。 但是，如果它导致意外的行为，你可以通过将以下项添加到应用配置文件的 `<appSettings>` 部分来禁用它：<br /><br /> `<add key="EntityFramework_SimplifyUserSpecifiedViews"  value="false" />`|边缘|  
  
## <a name="see-also"></a>另请参阅  
 [重定目标更改](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-2.md)   
 [4.5 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.1 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)
