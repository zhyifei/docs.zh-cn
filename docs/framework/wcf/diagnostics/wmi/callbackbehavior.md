---
title: CallbackBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c10d9e26f86fa569b1a607c9b755f32ee97792a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="callbackbehavior"></a>CallbackBehavior
CallbackBehavior  
  
## <a name="syntax"></a>语法  
  
```  
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>方法  
 CallbackBehavior 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 CallbackBehavior 类具有以下属性：  
  
### <a name="automaticsessionshutdown"></a>AutomaticSessionShutdown  
 数据类型：Boolean  
  
 访问类型：只读  
  
 如果为 true，则会话在服务关闭双工会话时自动关闭。  
  
### <a name="concurrencymode"></a>ConcurrencyMode  
 数据类型：String  
访问类型：只读  
  
 指定服务是支持一个线程、多个线程还是支持可重入调用。  
  
### <a name="ignoreextensiondataobject"></a>IgnoreExtensionDataObject  
 数据类型：Boolean  
  
 访问类型：只读  
  
 一个值，指定是否将未知序列化数据发送到网络上。  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 数据类型：Boolean  
  
 访问类型：只读  
  
 如果启用，则回调异常的详细信息被附加到服务所返回的错误中。  
  
### <a name="maxitemsinobjectgraph"></a>MaxItemsInObjectGraph  
 数据类型：Boolean  
  
 访问类型：只读  
  
 序列化对象中允许的最大项数。  
  
### <a name="usesynchronizationcontext"></a>UseSynchronizationContext  
 数据类型：Boolean  
  
 访问类型：只读  
  
 指定是否使用当前同步上下文来选择执行的线程。  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  
 数据类型：Boolean  
  
 访问类型：只读  
  
 指定系统或应用程序是否强制执行 SOAP MustUnderstand 标头处理。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
