---
title: <Directives>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 49c1aaf005b80a6c1c1fa382eebc2cb0dbfa4be7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181048"
---
# <a name="directives-element-net-native"></a>\<指令>元素（.NET 本机）
每个运行时指令文件中的根元素为 .NET 本机。  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a>语法  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`xmlns`|XML 命名空间。 它的价值总是 **""。http://schemas.microsoft.com/netfx/2013/01/metadata**|  
  
## <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<应用>](application-element-net-native.md)|作为应用程序范围内的类型和其元数据可以用于反射的类型成员的容器而服务。|  
|[\<图书馆>](library-element-net-native.md)|定义那些子类型和类型成员在运行时间要求元数据的程序集。|  
  
## <a name="remarks"></a>备注  
 每个运行时指令文件都可以只包含一个 `<Directives>` 元素。  
  
 该`<Directives>`元素可以包含零或一个[\<应用程序>](application-element-net-native.md)元素，以及零、一个或多个[\<库>](library-element-net-native.md)元素。  
  
## <a name="see-also"></a>另请参阅

- [运行时指令 (rd.xml) 配置文件引用](runtime-directives-rd-xml-configuration-file-reference.md)
- [运行时指令元素](runtime-directive-elements.md)
