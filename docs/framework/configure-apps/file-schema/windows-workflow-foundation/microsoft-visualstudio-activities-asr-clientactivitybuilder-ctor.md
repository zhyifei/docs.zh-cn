---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: b63f8917d7af21c165a16bd45a83e774bcec6e1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551600"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a>Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
创建的实例[Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)类。  
  
## <a name="syntax"></a>语法  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a>参数  
  
## <a name="parameter-values"></a>参数值  
 *operationDescription*  
  
 描述要在生成的工作流活动中执行的操作，包括操作名称、返回类型和参数信息。 此参数的值不能**null**。 它应描述使用消息协定并且取得具有一个消息的参数的同步操作。 如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。  
  
 *configurationName*  
  
 指定终结点配置名称。 此参数的值不能是**null**或为空。 如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。  
  
 *proxyNamespace*  
  
 指定操作的服务命名空间。 此参数的值不能是**null**或为空。 如果不满足这些条件，则使用此类的构造函数和其他方法的运行时结果未被定义。  
  
## <a name="see-also"></a>请参阅
- [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
