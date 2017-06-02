---
title: "封送处理字符串 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "数据封送处理, 平台调用"
  - "数据封送处理, 示例"
  - "数据封送处理, 字符串"
  - "封送处理, 平台调用"
  - "封送处理, 示例"
  - "封送处理. 字符串"
  - "平台调用, 封送处理数据"
  - "示例应用程序 [.NET Framework], 封送处理字符串"
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 封送处理字符串
平台调用复制字符串参数，并在必要时将其从 .NET Framework 格式 \(Unicode\) 转换为非托管格式 \(ANSI\)。  由于托管字符串是不可变的，因此当函数返回时，平台调用不会将它们从非托管内存复制回托管内存。  
  
 下表列出了字符串的封送处理选项，描述了它们的用法，并提供了到相应的 .NET Framework 示例的链接。  
  
|String|说明|示例|  
|------------|--------|--------|  
|通过值传递。|将字符串作为 In 参数传递。|[MsgBox](../../../docs/framework/interop/msgbox-sample.md)|  
|作为结果。|从非托管代码返回字符串。|[字符串](http://msdn.microsoft.com/zh-cn/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|通过引用传递。|使用 <xref:System.Text.StringBuilder> 将字符串作为 In\/Out 参数传递。|[Buffers](http://msdn.microsoft.com/zh-cn/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|在结构中通过值传递。|在作为 In 参数的结构中传递字符串。|[结构](http://msdn.microsoft.com/zh-cn/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|在结构中通过引用传递 **\(char\*\)**。|在作为 In\/Out 参数的结构中传递字符串。  非托管函数需要指向字符缓冲区的指针，并且缓冲区大小是结构的成员。|[字符串](http://msdn.microsoft.com/zh-cn/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|在结构中通过引用传递 **\(char\[\]\)**。|在作为 In\/Out 参数的结构中传递字符串。  非托管函数需要嵌入的字符缓冲区。|[OSInfo](http://msdn.microsoft.com/zh-cn/69d89067-507b-41fe-859d-30bf3ff29455)|  
|在类中通过值传递 **\(char\*\)**。|在作为 In\/Out 参数的类中传递字符串。  非托管函数需要指向字符缓冲区的指针。|[OpenFileDlg](http://msdn.microsoft.com/zh-cn/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|在类中通过值传递 **\(char\[\]\)**。|在作为 In\/Out 参数的类中传递字符串。  非托管函数需要嵌入的字符缓冲区。|[OSInfo](http://msdn.microsoft.com/zh-cn/69d89067-507b-41fe-859d-30bf3ff29455)|  
|作为通过值传递的字符串数组。|创建通过值传递的字符串数组。|[数组](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|作为包含通过值传递的字符串的结构数组。|创建包含字符串的结构数组，并且该数组是通过值传递的。|[数组](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## 请参阅  
 [用平台调用封送数据](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/zh-cn/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [封送类、结构和联合](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)   
 [Marshaling Arrays of Types](http://msdn.microsoft.com/zh-cn/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)   
 [Miscellaneous Marshaling Samples](http://msdn.microsoft.com/zh-cn/a915c948-54e9-4d0f-a525-95a77fd8ed70)