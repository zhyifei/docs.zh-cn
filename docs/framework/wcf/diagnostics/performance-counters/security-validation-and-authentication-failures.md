---
title: Security Validation and Authentication Failures（安全验证和身份验证失败次数）
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5d7964c59f28f33d6ec7bc3ba605b84e6a201b14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474254"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="33b4e-102">Security Validation and Authentication Failures（安全验证和身份验证失败次数）</span><span class="sxs-lookup"><span data-stu-id="33b4e-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="33b4e-103">计数器名称：Security Validation and Authentication Failures（安全验证和身份验证失败次数）</span><span class="sxs-lookup"><span data-stu-id="33b4e-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="33b4e-104">描述</span><span class="sxs-lookup"><span data-stu-id="33b4e-104">Description</span></span>  
 <span data-ttu-id="33b4e-105">每当消息由于“Security Calls Not Authorized”（未授权的安全调用次数）计数器中未包括的安全问题而遭到拒绝时，此计数器即会递增。</span><span class="sxs-lookup"><span data-stu-id="33b4e-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="33b4e-106">此类问题包括：</span><span class="sxs-lookup"><span data-stu-id="33b4e-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="33b4e-107">无法从消息中读取客户端令牌。</span><span class="sxs-lookup"><span data-stu-id="33b4e-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="33b4e-108">客户端令牌身份验证失败（如密码错误）。</span><span class="sxs-lookup"><span data-stu-id="33b4e-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="33b4e-109">签名验证失败（如消息已被篡改）。</span><span class="sxs-lookup"><span data-stu-id="33b4e-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="33b4e-110">消息与上一条消息重复，这种情况可能在重放攻击过程中发生。</span><span class="sxs-lookup"><span data-stu-id="33b4e-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="33b4e-111">已发生解密失败。</span><span class="sxs-lookup"><span data-stu-id="33b4e-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="33b4e-112">消息中缺少一些必需元素（如缺少时间戳或加密的数据块）。</span><span class="sxs-lookup"><span data-stu-id="33b4e-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="33b4e-113">TLSNEGO/SPNEGO 握手过程中已发生错误。</span><span class="sxs-lookup"><span data-stu-id="33b4e-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
