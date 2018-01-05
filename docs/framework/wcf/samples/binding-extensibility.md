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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13f17264aa1c82f882d799e6b69a974e8abdb133
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="binding-extensibility"></a><span data-ttu-id="b595d-102">绑定扩展性</span><span class="sxs-lookup"><span data-stu-id="b595d-102">Binding Extensibility</span></span>

<span data-ttu-id="b595d-103">本节包含演示 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中自定义绑定的示例。</span><span class="sxs-lookup"><span data-stu-id="b595d-103">This section contains samples that demonstrate custom binding in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b595d-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="b595d-104">In This Section</span></span>  
 <xref:System.ServiceModel.NetHttpBinding>  
 <span data-ttu-id="b595d-105">演示如何实现在 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 之上堆积 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> 或 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> 的绑定。</span><span class="sxs-lookup"><span data-stu-id="b595d-105">Demonstrates how to implement a binding that stacks <xref:System.ServiceModel.Channels.HttpTransportBindingElement> or the <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> on top of the <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span></span>  
  
 [<span data-ttu-id="b595d-106">WSStreamedHttpBinding</span><span class="sxs-lookup"><span data-stu-id="b595d-106">WSStreamedHttpBinding</span></span>](wsstreamedhttpbinding.md)  
 <span data-ttu-id="b595d-107">演示如何创建一个绑定，该绑定用于在使用 HTTP 传输时支持件流式传送方案。</span><span class="sxs-lookup"><span data-stu-id="b595d-107">Demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>  
