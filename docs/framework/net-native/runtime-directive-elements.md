---
title: "运行时指令元素 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 运行时指令元素
运行时指令 \(rd.xml\) 文件格式支持以下运行时指令元素。  请参阅[运行时指令 \(rd.xml\) 配置文件引用](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)以了解分层表示形式。  
  
 [\<应用程序\>](../../../docs/framework/net-native/application-element-net-native.md)  
 将运行时反射策略应用到该应用使用的所有类型，作为应用程序范围内的类型和元数据可以反应在运行时间的类型成员的容器而服务。  这是[\<指令\>](../../../docs/framework/net-native/directives-element-net-native.md)元素的子元素。  
  
 [\<程序集\>](../../../docs/framework/net-native/assembly-element-net-native.md)  
 将运行时策略应用到程序集中的所有类型。  这是[\<应用程序\>](../../../docs/framework/net-native/application-element-net-native.md)和[\<库\>](../../../docs/framework/net-native/library-element-net-native.md)元素的子元素。  
  
 [\<属性暗示\>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)  
 如果其包含[\<类型\>](../../../docs/framework/net-native/type-element-net-native.md)指令是一个特性，将运行时策略应用到该特性应用到的代码元素。  
  
 [\<指令\>](../../../docs/framework/net-native/directives-element-net-native.md)  
 根元素位于 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 的每个运行时指令文件中。  其子元素是[\<应用程序\>](../../../docs/framework/net-native/application-element-net-native.md)和[\<库\>](../../../docs/framework/net-native/library-element-net-native.md)。  
  
 [\<事件\>](../../../docs/framework/net-native/event-element-net-native.md)  
 将运行时策略应用到一个事件。  这是[\<类型\>](../../../docs/framework/net-native/type-element-net-native.md)和[\<类型实例化\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)元素的子元素。  
  
 [\<域\>](../../../docs/framework/net-native/field-element-net-native.md)  
 将运行时策略应用到一个字段。  这是[\<类型\>](../../../docs/framework/net-native/type-element-net-native.md)和[\<类型实例化\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)元素的子元素。  
  
 [\<泛型参数\>](../../../docs/framework/net-native/genericparameter-element-net-native.md)  
 将运行时策略应用到一个泛型类型或方法的参数类型。  
  
 [\<暗示类型\>](../../../docs/framework/net-native/impliestype-element-net-native.md)  
 如果该策略已应用到该包含类型或方法，将该运行时策略应用到一个类型。  
  
 [\<库\>](../../../docs/framework/net-native/library-element-net-native.md)  
 将运行时策略应用到程序集中的所有类型。  这是[\<应用程序\>](../../../docs/framework/net-native/application-element-net-native.md)和[\<库\>](../../../docs/framework/net-native/library-element-net-native.md)元素的子元素。  
  
 [\<方法\>](../../../docs/framework/net-native/method-element-net-native.md)  
 将运行时策略应用到一个方法。  这是[\<类型\>](../../../docs/framework/net-native/type-element-net-native.md)和[\<类型实例化\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)元素的子元素。  
  
 [\<方法实例化\>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)  
 将运行时策略应用到一个构造泛型方法。  这是[\<类型\>](../../../docs/framework/net-native/type-element-net-native.md)和[\<类型实例化\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)元素的子元素。  
  
 [\<命名空间\>](../../../docs/framework/net-native/namespace-element-net-native.md)  
 将运行时策略应用到命名空间中的所有类型。  
  
 [\<参数\>](../../../docs/framework/net-native/parameter-element-net-native.md)  
 将运行时策略应用到传递到方法的参数类型。  
  
 [\<属性\>](../../../docs/framework/net-native/property-element-net-native.md)  
 将运行时策略应用到一个属性。  这是[\<类型\>](../../../docs/framework/net-native/type-element-net-native.md)和[\<类型实例化\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)元素的子元素。  
  
 [\<子类型\>](../../../docs/framework/net-native/subtypes-element-net-native.md)  
 将运行时策略应用到从包含类型继承的所有类。  
  
 [\<类型\>](../../../docs/framework/net-native/type-element-net-native.md)  
 将运行时策略应用到一个类型。  
  
 [\<类型实例化\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)  
 将运行时策略应用到一个构造泛型类型。  
  
 [\<类型参数\>](../../../docs/framework/net-native/typeparameter-element-net-native.md)  
 将运行时策略应用到以传递到方法为代表的 <xref:System.Type> 参数类型。  
  
## 请参阅  
 [rd.xml 配置文件引用](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)