---
title: "迁移：minFreeMemoryPercentageToActiveService 配置设置 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# 迁移：minFreeMemoryPercentageToActiveService 配置设置
在 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 中，如果 Web 服务器上的可用内存小于 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 配置设置指定的百分比，则会引发异常。  在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，已忽略此设置。  
  
## 影响  
 在大多数情况下，遵循 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 设置的影响令人满意：它可防止在具有受约束内存的系统上启动 Windows Communication Foundation \(WCF\) 服务时可能发生的 <xref:System.OutOfMemoryException> 异常，从而提高系统稳定性。  
  
 但是在某些情况下，以前成功启动的服务可能会无法启动。  在这种情况下，会显示详细错误消息：  
  
```Output  
  
内存入口检查失败，因为可用内存(nnnn 字节)少于总内存的 nn%。  因此，该服务不可用于传入的请求。  若要解决此问题，请减少计算机上的负载，或调整 serviceHostingEnvironment 配置元素上的 minFreeMemoryPercentageToActivateService 值。    
```  
  
## 缓解操作  
 若要还原为忽略 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 设置的以前行为，请按如下所示修改 web.config 文件：  
  
```  
  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
  
```  
  
## 请参阅  
 [运行时更改](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)