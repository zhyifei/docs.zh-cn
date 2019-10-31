---
title: <relativeBindForResources> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: 6a418fc546313b74bb965a0b223eca9c2e5acc08
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115790"
---
# <a name="relativebindforresources-element"></a>\<relativeBindForResources > 元素
优化附属程序集的探测。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<relativeBindForResources >**  
  
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
  
|“值”|描述|  
|-----------|-----------------|  
|`false`|运行时不会优化附属程序集的探测。 此为默认值。|  
|`true`|运行时优化附属程序集的探测。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 一般情况下，资源管理器探测资源，如[打包和部署资源](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)主题中所述。 这意味着，当资源管理器探测某个资源的特定本地化版本时，它可能会在全局程序集缓存中查找，在应用程序的基本代码中查找特定于区域性的文件夹，为附属程序集查询 Windows Installer，并引发<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 事件。 `<relativeBindForResources>` 元素优化了资源管理器为附属程序集探测的方式。 当在以下条件下探测资源时，它可以提高性能：  
  
- 当附属程序集部署在与代码程序集相同的位置时。 换言之，如果代码程序集安装在全局程序集缓存中，则还必须在该程序集中安装附属程序集。 如果代码程序集安装在应用程序的代码库中，则附属程序集还必须安装在基本代码的特定于区域性的文件夹中。  
  
- 如果未使用 Windows Installer 或只是很少使用附属程序集的按需安装。  
  
- 当应用程序代码不处理 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 事件时。  
  
 将 `<relativeBindForResources>` 元素的 `enabled` 特性设置为 `true` 会优化资源管理器对附属程序集的探测，如下所示：  
  
- 它使用父代码程序集的位置来探测附属程序集。  
  
- 它不会为附属程序集查询 Windows Installer。  
  
- 它不会引发 <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 事件。  
  
## <a name="see-also"></a>请参阅

- [打包和部署资源](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
