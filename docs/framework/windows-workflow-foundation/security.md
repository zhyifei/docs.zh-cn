---
title: 安全性
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: cbfb82c2db329725d3445e1a88b54e01d5813f36
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348405"
---
# <a name="security"></a>安全性
SQL 工作流实例存储使用以下数据库安全角色确保安全访问持久性数据库中的实例状态信息。  
  
- **System.Activities.DurableInstancing.InstanceStoreUsers**。 此角色具有对公共视图的读写访问权以及对创建、加载和保存实例所涉及的存储过程的执行权限。  
  
- **System.Activities.DurableInstancing.InstanceStoreObservers**. 此角色具有对公共视图的只读访问权。  
  
- **System.Activities.DurableInstancing.WorkflowActivationUsers**。 此角色对在实例激活过程中涉及的存储过程具有执行权限。 有关实例激活的详细信息，请参阅[实例激活](instance-activation.md)。 泛型宿主 （如 Windows Server AppFabric 的承载功能工作流管理服务） 运行的用户帐户应添加到此数据库角色。  
  
 有关使用 Windows Server App Fabric 的持久性存储安全性的详细信息，请参阅[App Fabric 中持久性存储的安全配置](https://go.microsoft.com/fwlink/?LinkId=201208)  
  
> [!CAUTION]
>  有权访问自己存在实例存储区中的实例数据的客户端对同一实例存储区中所有其他实例也具有访问权限。 实例存储区不支持在实例级别指定安全权限。 您应创建单独的实例存储区并映射不同的组/用户，使他们有权访问的存储区有所不同。
