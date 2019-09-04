---
title: <disableCommitThreadStack> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fa32d64f3ce440981c5f26d731051a118ed9254
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252671"
---
# <a name="disablecommitthreadstack-element"></a>\<disableCommitThreadStack > 元素
指定在线程启动时是否提交完整线程堆栈。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<disableCommitThreadStack>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|enabled|必需的特性。<br /><br /> 指定是否禁止在线程启动时提交完整线程堆栈（默认行为）。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|Description|  
|-----------|-----------------|  
|0|不禁用公共语言运行时的默认行为（即在线程启动时提交完整线程堆栈）。|  
|1|禁用公共语言运行时的默认行为（即在线程启动时提交完整线程堆栈）。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 公共语言运行时的默认行为是在线程启动时提交完整线程堆栈。 当必须在内存有限的服务器上创建大量线程，并且其中大多数线程都使用非常小的堆栈空间时，如果公共语言运行时在线程启动时不立即提交完整线程堆栈，则服务器可能会表现更好。  
  
> [!NOTE]
> 非托管主机可以使用 `STARTUP_DISABLE_COMMITTHREADSTACK` STARTUP_FLAGS [枚举中的](../../../unmanaged-api/hosting/startup-flags-enumeration.md) 启动标志实现相同结果。  
  
## <a name="example"></a>示例  
 下面的示例演示如何禁用公共语言运行时的默认行为（即在线程启动时提交完整线程堆栈）。  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
