---
title: TraceListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2c0b595-a384-4eb3-b94d-1b3be7cc7a5c
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c0bba558a7b0c727dd971960ab3f9120a6aaada
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="tracelistener"></a>TraceListener
TraceListener。  
  
## <a name="syntax"></a>语法  
  
```  
class TraceListener  
{  
  string Name;  
  TraceListenerArgument TraceListenerArguments[];  
};  
```  
  
## <a name="methods"></a>方法  
 TraceListener 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 TraceListener 类具有以下属性：  
  
### <a name="name"></a>名称  
 数据类型：String  
  
 访问类型：只读  
  
 跟踪侦听器的名称。  
  
### <a name="tracelistenerarguments"></a>TraceListenerArguments  
 数据类型：TraceListenerArgument 数组  
  
 访问类型：只读  
  
 跟踪侦听器的参数。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|
