---
title: '&lt;comContracts&gt;'
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: b44c09e7e32129ba21834f7fbb8dc4699904e46b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746405"
---
# <a name="ltcomcontractsgt"></a>&lt;comContracts&gt;
`comContracts` 配置节所包含的元素允许指定 COM+ 集成服务协定的各个属性。  
  
## <a name="specifying-namespace-and-contract"></a>指定命名空间和协定  
 COM + 集成服务协定是当前只限于" http://tempuri.org "命名空间，而协定名称从支持的 COM 接口派生。 但是，可以使用配置文件中的 `comContracts` 节来指定替代服务协定。  
  
 例如，可以使用以下配置来指定服务协定的命名空间和协定名称，也可以指定某个选项以在会话绑定上强制使用。  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
  </comContract>  
</comContracts>  
```  
  
 在初始化服务时，指定的命名空间和协定名称将应用到生成的服务说明。  
  
 当此节为空时，服务初始化将应用取自提供支持的 COM 接口 ID 的默认命名空间和协定名称。  
  
 此外，你可以使用[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素，用于指定 COM + 组件上的接口作为 Web 服务公开时公开的 COM + 方法。 你还可以使用[ \<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)指定持久类型在集成中使用。 最后，你可以使用[ \<userDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)元素以包含用户定义类型 (UDT) 都要包括在服务协定。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)  
 [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)  
 [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)  
 [\<comContract>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)  
 [与 COM+ 应用程序集成](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [如何：配置 COM+ 服务设置](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
