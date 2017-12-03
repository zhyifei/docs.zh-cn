---
title: MSMQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15be4b6bfb84a0aa843e3d62861a9195e125a04e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="msmq"></a><span data-ttu-id="ae558-102">MSMQ</span><span class="sxs-lookup"><span data-stu-id="ae558-102">MSMQ</span></span>
<span data-ttu-id="ae558-103">在 MSMQ 应用程序中，不会在 MSMQ 与队列通道之间传输任何额外活动。</span><span class="sxs-lookup"><span data-stu-id="ae558-103">In an MSMQ application, no additional activity is transferred from the queued channel to MSMQ and from MSMQ to the queued channel.</span></span>  
  
 <span data-ttu-id="ae558-104">另外，在执行 Send（发送）操作和 Receive（接收）操作时，还将 MSMQ 消息 ID 和 SOAP 消息 ID（连同活动 ID，如果存在）</span><span class="sxs-lookup"><span data-stu-id="ae558-104">In addition, MSMQ Message ID and SOAP message ID (along with Activity ID, if one exists) are traced as part of queued channel traces on a Send operation.</span></span>  
  
 <span data-ttu-id="ae558-105">作为队列通道跟踪的一部分来跟踪。</span><span class="sxs-lookup"><span data-stu-id="ae558-105">MSMQ Message ID and SOAP message ID (along with activity ID, if one exists) are traced as part of queued channel traces on a Receive operation.</span></span>  
  
 <span data-ttu-id="ae558-106">Receive（接收）操作所要求的传输的执行方式类似于其他任何传输（接收字节->处理消息->操作）。</span><span class="sxs-lookup"><span data-stu-id="ae558-106">The required transfers on the Receive operation are executed similarly to any other transport (receive bytes->Process message-> operation).</span></span>
