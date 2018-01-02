---
title: "&lt;PreferComInsteadOfManagedRemoting&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad60d73e30bf02fd52f9c8f3bd707b571959bdd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a>&lt;PreferComInsteadOfManagedRemoting&gt;元素
指定是否运行时将使用 COM 互操作而不是远程处理所有调用跨应用程序域边界。  
  
 \<configuration>  
\<运行时 >  
\<PreferComInsteadOfManagedRemoting >  
  
## <a name="syntax"></a>语法  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指示运行时将使用 COM 互操作而不是远程处理跨应用程序域边界。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`false`|运行时将跨应用程序域边界使用远程处理。 这是默认设置。|  
|`true`|运行时将跨应用程序域边界使用 COM 互操作。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 当你将设置`enabled`属性设为`true`，运行时的行为，如下所示：  
  
-   运行时不会调用[iunknown:: Queryinterface](http://go.microsoft.com/fwlink/?LinkID=144867)为[IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)接口时[IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003)接口进入通过 COM 接口域。 相反，它构造[运行时可调用包装器](../../../../../docs/framework/interop/runtime-callable-wrapper.md)(RCW) 针对对象。  
  
-   在接收时，则运行时将返回 E_NOINTERFACE`QueryInterface`寻求[IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)任何接口[COM 可调用包装](../../../../../docs/framework/interop/com-callable-wrapper.md)(CCW) 已在此域中创建。  
  
 请确保这两种行为，COM 上的所有调用之间的都接口的托管的对象跨应用程序域边界使用 COM 和 COM 互操作而不是远程处理。  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定运行时应使用 COM 互操作跨隔离边界：  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)
