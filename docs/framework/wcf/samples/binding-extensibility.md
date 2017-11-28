---
title: "绑定扩展性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cabdd583-ddf5-493e-9dba-c6c31cde8f65
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61c8ae647012c5f1fffe5cf65c63b64cde62af1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="binding-extensibility"></a>绑定扩展性
本节包含演示 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中自定义绑定的示例。  
  
## <a name="in-this-section"></a>本节内容  
 <xref:System.ServiceModel.NetHttpBinding>  
 演示如何实现在 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 之上堆积 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> 或 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> 的绑定。  
  
 <!--zz <xref:System.ServiceModel.WSStreamedHttpBinding> --> `System.ServiceModel.WSStreamedHttpBinding` 
 演示如何创建一个绑定，该绑定用于在使用 HTTP 传输时支持件流式传送方案。
