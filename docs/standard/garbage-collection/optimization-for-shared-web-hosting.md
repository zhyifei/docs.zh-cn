---
title: "针对共享 Web 承载优化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f423d867d4fada075800650627c94f9d09e9e7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="optimization-for-shared-web-hosting"></a>针对共享 Web 承载优化
如果你是通过承载多个小型网站共享的服务器的管理员，你可以优化性能并通过添加以下增加站点容量`gcTrimCommitOnLowMemory`将设置为`runtime`.NET 中的 Aspnet.config 文件中的节点目录：  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  此设置仅建议的共享 Web 承载方案。  
  
 由于垃圾回收器会保留供将来分配的内存，其提交的空间可以是多个真正需要的。 你可以减少此空间以容纳时间的负荷较重的系统内存时。 减小此提交的空间会改进性能，并扩展容量，以承载多个站点。  
  
 当`gcTrimCommitOnLowMemory`设置启用，垃圾回收器计算结果的系统内存加载和负载达到 90%时，将进入修整模式。 这样可保持修整模式，直到负载下下降 85%。  
  
 如果条件允许，垃圾回收器可以决定`gcTrimCommitOnLowMemory`设置而不会帮助当前应用程序并且忽略它。  
  
## <a name="example"></a>示例  
 以下 XML 片段演示如何启用`gcTrimCommitOnLowMemory`设置。 省略号表示词都会出现在其他设置`runtime`节点。  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅  
 [垃圾回收](../../../docs/standard/garbage-collection/index.md)
