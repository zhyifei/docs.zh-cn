---
title: "比较 COM+ 和 ServiceModel 中的事务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 712f8a7a153d7255275ff7ebaa647d5a624f8ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>比较 COM+ 和 ServiceModel 中的事务
本主题讨论如何使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 命名空间提供的 <xref:System.ServiceModel> 属性来模拟事务性 COM+ 服务的行为。  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>使用 ServiceModel 属性模拟 COM+  
 下表比较用于创建 <xref:System.EnterpriseServices.TransactionOption> 事务的 `EnterpriseServices` 枚举，以及他们如何与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的 <xref:System.ServiceModel> 属性关联。  
  
|COM+ 属性|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 属性|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|将 <xref:System.ServiceModel.TransactionFlowAttribute> 设置为 <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>。<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 为 `true`。<br /><br /> 绑定元素中的 `TransactionFlow` 属性为 `false`。|  
|必需|将 <xref:System.ServiceModel.TransactionFlowAttribute> 设置为 <xref:System.ServiceModel.TransactionFlowOption.Allowed>。<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 为 `true`。<br /><br /> 绑定元素中的 `TransactionFlow` 属性为 `true`。|  
|支持|没有直接等效项。 通常，您应采用为 `Required` 指定的行为。|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 为 `false`。<br /><br /> 绑定元素中的 `TransactionFlow` 属性为 `false`。|  
|Disabled|没有直接等效项。 通常，您应采用为 `NotSupported` 指定的行为。|
