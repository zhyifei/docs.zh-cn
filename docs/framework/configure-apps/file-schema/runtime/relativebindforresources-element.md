---
title: '&lt;relativeBindForResources&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ae5d1ca6403d84c9828dcf9550e9fbf40b28e1b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltrelativebindforresourcesgt-element"></a>&lt;relativeBindForResources&gt;元素
优化附属程序集的探测。  
  
 \<配置 > 元素  
\<运行时 > 元素  
\<relativeBindForResources > 元素  
  
## <a name="syntax"></a>语法  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定公共语言运行时是否优化附属程序集的探测。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`false`|运行时并不优化附属程序集的探测。 这是默认值。|  
|`true`|运行时优化附属程序集的探测。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 一般情况下，资源管理器来探测程序资源，如中所述[打包和部署资源](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)主题。 这意味着，当资源管理器来探测程序特定的本地化版本的资源，它可能在全局程序集缓存中查找，并在应用程序的代码的基础，查询 Windows Installer 的区域性特定文件夹中查找的附属程序集，而引发<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>事件。 `<relativeBindForResources>`元素优化资源管理器寻找附属程序集的方式。 探测以下条件下的资源时，它可以提高性能：  
  
-   当的附属程序集部署在与代码程序集相同的位置。 换而言之，如果代码程序集安装在全局程序集缓存，附属程序集必须也存在安装。 如果代码程序集安装在应用程序的基本代码，那么还必须在基本代码中的区域性特定文件夹中安装的附属程序集。  
  
-   当 Windows Installer 未使用，或只是偶尔使用按需安装的附属程序集。  
  
-   当应用程序代码不处理<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>事件。  
  
 设置`enabled`属性`<relativeBindForResources>`元素`true`优化资源管理器的探测附属程序集，如下所示：  
  
-   它使用父代码程序集的位置来探测程序的附属程序集。  
  
-   它不附属程序集的查询 Windows Installer。  
  
-   它不会引发<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>事件。  
  
## <a name="see-also"></a>请参阅  
 [打包和部署资源](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)
