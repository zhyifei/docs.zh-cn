---
title: 比较 COM+ 和 ServiceModel 中的事务
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 4a47fe1686dff2e705b06b001d7d5e4ea6e8c5f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857865"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>比较 COM+ 和 ServiceModel 中的事务
本主题讨论如何来模拟事务性 COM + 服务使用 Windows Communication Foundation (WCF) 属性的行为<xref:System.ServiceModel>命名空间提供。  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>使用 ServiceModel 属性模拟 COM+  
 下表比较<xref:System.EnterpriseServices.TransactionOption>枚举，用于创建`EnterpriseServices`事务和如何将 WCF 属性的关联<xref:System.ServiceModel>命名空间提供。  
  
|COM+ 属性|WCF 属性|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|将 <xref:System.ServiceModel.TransactionFlowAttribute> 设置为 <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>。<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 为 `true`。<br /><br /> 绑定元素中的 `TransactionFlow` 属性为 `false`。|  
|必需|将 <xref:System.ServiceModel.TransactionFlowAttribute> 设置为 <xref:System.ServiceModel.TransactionFlowOption.Allowed>。<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 为 `true`。<br /><br /> 绑定元素中的 `TransactionFlow` 属性为 `true`。|  
|支持|没有直接等效项。 通常，您应采用为 `Required` 指定的行为。|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 为 `false`。<br /><br /> 绑定元素中的 `TransactionFlow` 属性为 `false`。|  
|已禁用|没有直接等效项。 通常，您应采用为 `NotSupported` 指定的行为。|
