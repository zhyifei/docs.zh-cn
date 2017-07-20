---
title: "&lt;指令&gt;元素 (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# &lt;指令&gt;元素 (.NET Native)
根元素位于 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 的每个运行时指令文件中。  
  
 **\<Directives xmlns\="http:\/\/schemas.microsoft.com\/netfx\/2013\/01\/metadata"\>**  
  
## 语法  
  
```xml  
  
        <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## 特性  
  
|特性|描述|  
|--------|--------|  
|`xmlns`|XML 命名空间。  它的值始终为 **"http:\/\/schemas.microsoft.com\/netfx\/2013\/01\/metadata"**。|  
  
## 子元素  
  
|元素|描述|  
|--------|--------|  
|[\<应用程序\>](../../../docs/framework/net-native/application-element-net-native.md)|作为应用程序范围内的类型和其元数据可以用于反射的类型成员的容器而服务。|  
|[\<库\>](../../../docs/framework/net-native/library-element-net-native.md)|定义那些子类型和类型成员在运行时间要求元数据的程序集。|  
  
## 备注  
 每个运行时指令文件都可以只包含一个 `<Directives>` 元素。  
  
 `<Directives>` 元素可以包含零个或一个[\<应用程序\>](../../../docs/framework/net-native/application-element-net-native.md)元素，以及零个、一个或多个[\<库\>](../../../docs/framework/net-native/library-element-net-native.md)元素。  
  
## 请参阅  
 [运行时指令 \(rd.xml\) 配置文件引用](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [运行时指令元素](../../../docs/framework/net-native/runtime-directive-elements.md)