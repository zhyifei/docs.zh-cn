---
title: "WS-MetadataExchange 绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d305f3bf34b3b14da566fa792552e24e695ef33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="1dd53-102">WS-MetadataExchange 绑定</span><span class="sxs-lookup"><span data-stu-id="1dd53-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="1dd53-103">本主题说明如何为各种传输构造默认的元数据交换绑定。</span><span class="sxs-lookup"><span data-stu-id="1dd53-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="1dd53-104">默认绑定</span><span class="sxs-lookup"><span data-stu-id="1dd53-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="1dd53-105">默认绑定名称</span><span class="sxs-lookup"><span data-stu-id="1dd53-105">Default Binding Name</span></span>|<span data-ttu-id="1dd53-106">绑定的构造方式</span><span class="sxs-lookup"><span data-stu-id="1dd53-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="1dd53-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="1dd53-107">MexHttpBinding</span></span>|<span data-ttu-id="1dd53-108">一个禁用传输级安全性的 <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="1dd53-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="1dd53-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="1dd53-109">MexHttpsBinding</span></span>|<span data-ttu-id="1dd53-110">一个支持传输级安全性的 <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="1dd53-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="1dd53-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="1dd53-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="1dd53-112">一个 <xref:System.ServiceModel.Channels.CustomBinding>，它具有使用默认值的 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="1dd53-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="1dd53-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="1dd53-113">MexTcpBinding</span></span>|<span data-ttu-id="1dd53-114">一个 <xref:System.ServiceModel.Channels.CustomBinding>，它具有使用默认值的 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="1dd53-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
