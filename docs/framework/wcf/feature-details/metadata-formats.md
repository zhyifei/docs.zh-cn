---
title: "元数据格式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b7812023fbe2159daba205727e20e1b69b84686
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="metadata-formats"></a><span data-ttu-id="5e227-102">元数据格式</span><span class="sxs-lookup"><span data-stu-id="5e227-102">Metadata Formats</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="5e227-103"> 支持下表中的元数据格式。</span><span class="sxs-lookup"><span data-stu-id="5e227-103"> supports the metadata formats in the following table.</span></span>  
  
## <a name="metadata-specifications-and-usage"></a><span data-ttu-id="5e227-104">元数据的规范和用法</span><span class="sxs-lookup"><span data-stu-id="5e227-104">Metadata Specifications and Usage</span></span>  
  
|<span data-ttu-id="5e227-105">协议</span><span class="sxs-lookup"><span data-stu-id="5e227-105">Protocol</span></span>|<span data-ttu-id="5e227-106">规范和用法</span><span class="sxs-lookup"><span data-stu-id="5e227-106">Specification and usage</span></span>|  
|--------------|-----------------------------|  
|<span data-ttu-id="5e227-107">WSDL 1.1</span><span class="sxs-lookup"><span data-stu-id="5e227-107">WSDL 1.1</span></span>|[<span data-ttu-id="5e227-108">Web 服务描述语言 (WSDL) 1.1</span><span class="sxs-lookup"><span data-stu-id="5e227-108">Web Services Description Language (WSDL) 1.1</span></span>](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5e227-109"> 使用 Web 服务描述语言 (WSDL) 描述服务。</span><span class="sxs-lookup"><span data-stu-id="5e227-109"> uses Web Services Description Language (WSDL) to describe services.</span></span>|  
|<span data-ttu-id="5e227-110">XML 架构</span><span class="sxs-lookup"><span data-stu-id="5e227-110">XML Schema</span></span>|<span data-ttu-id="5e227-111">[XML 架构第 2 部分： 数据类型第二版](http://go.microsoft.com/fwlink/?LinkId=94861)和[XML 架构第 1 部分： 结构第二版](http://go.microsoft.com/fwlink/?LinkId=94862)</span><span class="sxs-lookup"><span data-stu-id="5e227-111">[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) and [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)</span></span><br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5e227-112"> 使用 XML 架构描述消息中使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5e227-112"> uses the XML Schema to describe data types used in messages.</span></span>|  
|<span data-ttu-id="5e227-113">WS Policy</span><span class="sxs-lookup"><span data-stu-id="5e227-113">WS Policy</span></span>|[<span data-ttu-id="5e227-114">Web 服务策略 1.2-框架 (Ws-policy)</span><span class="sxs-lookup"><span data-stu-id="5e227-114">Web Services Policy 1.2 - Framework (WS-Policy)</span></span>](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [<span data-ttu-id="5e227-115">Web 服务策略 1.5-框架</span><span class="sxs-lookup"><span data-stu-id="5e227-115">Web Services Policy 1.5 - Framework</span></span>](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5e227-116"> 将 WS-Policy 1.2 或 1.5 规范与特定于域的断言一起使用来描述服务要求和功能。</span><span class="sxs-lookup"><span data-stu-id="5e227-116"> uses the WS-Policy 1.2 or 1.5 specifications with domain-specific assertions to describe service requirements and capabilities.</span></span>|  
|<span data-ttu-id="5e227-117">WS Policy 附件</span><span class="sxs-lookup"><span data-stu-id="5e227-117">WS Policy Attachments</span></span>|[<span data-ttu-id="5e227-118">Web 服务策略 1.2-附件 (Ws-policyattachment)</span><span class="sxs-lookup"><span data-stu-id="5e227-118">Web Services Policy 1.2 - Attachment (WS-PolicyAttachment)</span></span>](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5e227-119"> 实现 WS-Policy 附件以在 WSDL 中的不同范围附加策略表达式。</span><span class="sxs-lookup"><span data-stu-id="5e227-119"> implements WS-Policy Attachments to attach policy expressions at various scopes in WSDL.</span></span>|  
|<span data-ttu-id="5e227-120">WS 元数据交换</span><span class="sxs-lookup"><span data-stu-id="5e227-120">WS Metadata Exchange</span></span>|[<span data-ttu-id="5e227-121">Web 服务元数据交换 (Ws-metadataexchange) 1.1 版</span><span class="sxs-lookup"><span data-stu-id="5e227-121">Web Services Metadata Exchange (WS-MetadataExchange) version 1.1</span></span>](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5e227-122"> 实现 WS-MetadataExchange 以检索 XML 架构、WSDL 和 WS-Policy。</span><span class="sxs-lookup"><span data-stu-id="5e227-122"> implements WS-MetadataExchange to retrieve XML Schema, WSDL, and WS-Policy.</span></span>|  
|<span data-ttu-id="5e227-123">WSDL 的 WS 寻址绑定</span><span class="sxs-lookup"><span data-stu-id="5e227-123">WS Addressing Binding for WSDL</span></span>|[<span data-ttu-id="5e227-124">Web 服务寻址 1.0-WSDL 绑定</span><span class="sxs-lookup"><span data-stu-id="5e227-124">Web Services Addressing 1.0 - WSDL Binding</span></span>](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5e227-125"> 实现 WSDL 的 WS-Addressing 绑定以在 WSDL 中附加寻址信息。</span><span class="sxs-lookup"><span data-stu-id="5e227-125"> implements WS-Addressing Binding for WSDL to attach addressing information in WSDL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e227-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e227-126">See Also</span></span>  
 [<span data-ttu-id="5e227-127">系统提供的互操作性绑定支持的 Web 服务协议</span><span class="sxs-lookup"><span data-stu-id="5e227-127">Web Services Protocols Supported by System-Provided Interoperability Bindings</span></span>](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [<span data-ttu-id="5e227-128">WSDL 和策略</span><span class="sxs-lookup"><span data-stu-id="5e227-128">WSDL and Policy</span></span>](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
