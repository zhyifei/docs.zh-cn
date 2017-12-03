---
title: TextMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 966f1ae06f5d7e0dacb8b7d450463c75f783ef1f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="textmessageencodingbindingelement"></a>TextMessageEncodingBindingElement
TextMessageEncodingBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>方法  
 TextMessageEncodingBindingElement 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 TextMessageEncodingBindingElement 类具有下列属性：  
  
### <a name="encoding"></a>编码  
 数据类型：String  
  
 访问类型：只读  
  
 要用来在绑定上发出消息的字符集编码。  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 数据类型：sint32  
  
 访问类型：只读  
  
 一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 数据类型：sint32  
  
 访问类型：只读  
  
 一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。  
  
### <a name="readerquotas"></a>ReaderQuotas  
 数据类型：XmlDictionaryReaderQuotas  
  
 访问类型：只读  
  
 读取器的配额。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
