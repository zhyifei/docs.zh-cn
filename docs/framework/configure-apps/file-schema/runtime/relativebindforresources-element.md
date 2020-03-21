---
title: <relativeBindForResources> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153901"
---
# <a name="relativebindforresources-element"></a>\<相对绑定资源>元素
优化附属程序集的探测。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<相对绑定资源>**  
  
## <a name="syntax"></a>语法  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定通用语言运行时是否优化了附属程序集的探测。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|说明|  
|-----------|-----------------|  
|`false`|运行时不优化卫星组件的探测。 这是默认值。|  
|`true`|运行时优化了卫星组件的探测。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 通常，资源管理器会调查资源，如["打包和部署资源](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)"主题中所述。 这意味着，当资源管理器探测资源的特定本地化版本时，它可能会查看全局程序集缓存、在应用程序代码库中查看特定于区域性的文件夹、查询 Windows 安装程序以查找附属程序集以及引发<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>事件。 该`<relativeBindForResources>`元素优化了资源管理器探测附属程序集的方式。 在以下条件下探测资源时，它可以提高性能：  
  
- 当附属程序集部署在同一位置的代码程序集时。 换句话说，如果代码程序集安装在全局程序集缓存中，则还必须在那里安装附属程序集。 如果代码程序集安装在应用程序的代码库中，则附属程序集也必须安装在代码库中特定于区域性的文件夹中。  
  
- 当不使用 Windows 安装程序或很少用于按需安装附属程序集时。  
  
- 当应用程序代码不处理事件<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>时。  
  
 设置`enabled``<relativeBindForResources>`元素的属性以`true`优化资源管理器对附属程序集的探测，如下所示：  
  
- 它使用父代码程序集的位置来探测附属程序集。  
  
- 它不查询 Windows 安装程序的附属程序集。  
  
- 它不引发事件<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>。  
  
## <a name="see-also"></a>另请参阅

- [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
