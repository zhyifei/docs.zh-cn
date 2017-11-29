---
title: "Security Validation and Authentication Failures Per Second（每秒安全验证和身份验证失败次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 39ddfd18caae33e7ac2b905488bdfe4a8c9dc520
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="65eaa-102">Security Validation and Authentication Failures Per Second（每秒安全验证和身份验证失败次数）</span><span class="sxs-lookup"><span data-stu-id="65eaa-102">Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="65eaa-103">计数器名称：Security Validation and Authentication Failures Per Second（每秒安全验证和身份验证失败次数）。</span><span class="sxs-lookup"><span data-stu-id="65eaa-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="65eaa-104">描述</span><span class="sxs-lookup"><span data-stu-id="65eaa-104">Description</span></span>  
 <span data-ttu-id="65eaa-105">每当消息由于“Security Calls Not Authorized”（未授权的安全调用次数）计数器中未包括的安全问题而遭到拒绝时，此计数器即会递增。</span><span class="sxs-lookup"><span data-stu-id="65eaa-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="65eaa-106">此类问题包括：</span><span class="sxs-lookup"><span data-stu-id="65eaa-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="65eaa-107">无法从消息中读取客户端令牌。</span><span class="sxs-lookup"><span data-stu-id="65eaa-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="65eaa-108">客户端令牌身份验证失败（如密码错误）。</span><span class="sxs-lookup"><span data-stu-id="65eaa-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="65eaa-109">签名验证失败（如消息已被篡改）。</span><span class="sxs-lookup"><span data-stu-id="65eaa-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="65eaa-110">消息与上一条消息重复，这种情况可能在重放攻击过程中发生。</span><span class="sxs-lookup"><span data-stu-id="65eaa-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="65eaa-111">已发生解密失败。</span><span class="sxs-lookup"><span data-stu-id="65eaa-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="65eaa-112">消息中缺少一些必需元素（如缺少时间戳或加密的数据块）。</span><span class="sxs-lookup"><span data-stu-id="65eaa-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="65eaa-113">TLSNEGO/SPNEGO 握手过程中已发生错误。</span><span class="sxs-lookup"><span data-stu-id="65eaa-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="65eaa-114">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值：</span><span class="sxs-lookup"><span data-stu-id="65eaa-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="65eaa-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="65eaa-115">(N1-N0)/((D1-D0)/F)</span></span>
