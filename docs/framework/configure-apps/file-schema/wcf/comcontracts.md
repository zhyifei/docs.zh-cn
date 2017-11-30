---
title: '&lt;comContracts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 168bd57652aca5f3c1b61c90abea5288bd1a6719
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcomcontractsgt"></a><span data-ttu-id="e34c8-102">&lt;comContracts&gt;</span><span class="sxs-lookup"><span data-stu-id="e34c8-102">&lt;comContracts&gt;</span></span>
<span data-ttu-id="e34c8-103">`comContracts` 配置节所包含的元素允许指定 COM+ 集成服务协定的各个属性。</span><span class="sxs-lookup"><span data-stu-id="e34c8-103">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="e34c8-104">指定命名空间和协定</span><span class="sxs-lookup"><span data-stu-id="e34c8-104">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="e34c8-105">COM + 集成服务协定当前只限于"http://tempuri.org"命名空间，而协定名称从支持的 COM 接口派生。</span><span class="sxs-lookup"><span data-stu-id="e34c8-105">COM+ integration service contracts are currently restricted to the "http://tempuri.org" namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="e34c8-106">但是，可以使用配置文件中的 `comContracts` 节来指定替代服务协定。</span><span class="sxs-lookup"><span data-stu-id="e34c8-106">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="e34c8-107">例如，可以使用以下配置来指定服务协定的命名空间和协定名称，也可以指定某个选项以在会话绑定上强制使用。</span><span class="sxs-lookup"><span data-stu-id="e34c8-107">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
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
  
 <span data-ttu-id="e34c8-108">在初始化服务时，指定的命名空间和协定名称将应用到生成的服务说明。</span><span class="sxs-lookup"><span data-stu-id="e34c8-108">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="e34c8-109">当此节为空时，服务初始化将应用取自提供支持的 COM 接口 ID 的默认命名空间和协定名称。</span><span class="sxs-lookup"><span data-stu-id="e34c8-109">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="e34c8-110">此外，你可以使用[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素，用于指定 COM + 组件上的接口作为 Web 服务公开时公开的 COM + 方法。</span><span class="sxs-lookup"><span data-stu-id="e34c8-110">In addition, you can use the [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="e34c8-111">你还可以使用[ \<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)指定持久类型在集成中使用。</span><span class="sxs-lookup"><span data-stu-id="e34c8-111">You can also use the [\<persistableTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="e34c8-112">最后，你可以使用[ \<userDefinedType >](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)元素以包含用户定义类型 (UDT) 都要包括在服务协定。</span><span class="sxs-lookup"><span data-stu-id="e34c8-112">Finally, you can use the [\<userDefinedType>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e34c8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e34c8-113">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="e34c8-114">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="e34c8-114">\<exposedMethod></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)  
 [<span data-ttu-id="e34c8-115">\<persistableTypes ></span><span class="sxs-lookup"><span data-stu-id="e34c8-115">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)  
 [<span data-ttu-id="e34c8-116">\<userDefinedType ></span><span class="sxs-lookup"><span data-stu-id="e34c8-116">\<userDefinedType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)  
 [<span data-ttu-id="e34c8-117">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="e34c8-117">\<comContract></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)  
 [<span data-ttu-id="e34c8-118">与 COM + 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="e34c8-118">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="e34c8-119">如何： 配置 COM + 服务设置</span><span class="sxs-lookup"><span data-stu-id="e34c8-119">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
