---
title: 服务：Security Validation and Authentication Failures（安全验证和身份验证失败次数）
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: ba8da3ae6be6bd089690359f19e153da1e0b54fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998304"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="42b0f-102">服务：Security Validation and Authentication Failures（安全验证和身份验证失败次数）</span><span class="sxs-lookup"><span data-stu-id="42b0f-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="42b0f-103">计数器名称：Security Validation and Authentication Failures（安全验证和身份验证失败次数）</span><span class="sxs-lookup"><span data-stu-id="42b0f-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="42b0f-104">描述</span><span class="sxs-lookup"><span data-stu-id="42b0f-104">Description</span></span>  
 <span data-ttu-id="42b0f-105">每当消息由于“Security Calls Not Authorized”（未授权的安全调用次数）计数器中未包括的安全问题而遭到拒绝时，此计数器即会递增。</span><span class="sxs-lookup"><span data-stu-id="42b0f-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="42b0f-106">此类问题包括：</span><span class="sxs-lookup"><span data-stu-id="42b0f-106">Such problems include:</span></span>  
  
- <span data-ttu-id="42b0f-107">无法从消息中读取客户端令牌。</span><span class="sxs-lookup"><span data-stu-id="42b0f-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="42b0f-108">客户端令牌身份验证失败（如密码错误）。</span><span class="sxs-lookup"><span data-stu-id="42b0f-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
- <span data-ttu-id="42b0f-109">签名验证失败（如消息已被篡改）。</span><span class="sxs-lookup"><span data-stu-id="42b0f-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
- <span data-ttu-id="42b0f-110">消息与上一条消息重复，这种情况可能在重放攻击过程中发生。</span><span class="sxs-lookup"><span data-stu-id="42b0f-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="42b0f-111">已发生解密失败。</span><span class="sxs-lookup"><span data-stu-id="42b0f-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="42b0f-112">消息中缺少一些必需元素（如缺少时间戳或加密的数据块）。</span><span class="sxs-lookup"><span data-stu-id="42b0f-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="42b0f-113">TLSNEGO/SPNEGO 握手过程中已发生错误。</span><span class="sxs-lookup"><span data-stu-id="42b0f-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
