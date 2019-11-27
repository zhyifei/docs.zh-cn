---
title: FIPS 相容性-.NET Core
description: 介绍 .NET Core 美国联邦信息处理标准（FIPS）符合性。
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: cf640c857e79ae811dd38d57a0e5301b7bc96572
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2019
ms.locfileid: "74205076"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="c2129-103">.NET Core 美国联邦信息处理标准（FIPS）符合性</span><span class="sxs-lookup"><span data-stu-id="c2129-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="c2129-104">美国联邦信息处理标准（FIPS）发布140-2 是美国政府标准，用于定义信息技术产品中加密模块的最低安全要求，如信息的第5131节中所定义技术管理改革行为1996。</span><span class="sxs-lookup"><span data-stu-id="c2129-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="c2129-105">.NET Core：</span><span class="sxs-lookup"><span data-stu-id="c2129-105">.NET Core:</span></span>

* <span data-ttu-id="c2129-106">将加密基元调用传递到基础操作系统提供的标准模块。</span><span class="sxs-lookup"><span data-stu-id="c2129-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="c2129-107">**不**强制在 .net Core 应用程序中使用 FIPS 批准的算法或密钥大小。</span><span class="sxs-lookup"><span data-stu-id="c2129-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="c2129-108">系统管理员负责为操作系统配置 FIPS 相容性。</span><span class="sxs-lookup"><span data-stu-id="c2129-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="c2129-109">如果为符合 FIPS 标准的环境编写代码，开发人员负责确保不会使用不合规的 FIPS 算法。</span><span class="sxs-lookup"><span data-stu-id="c2129-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="c2129-110">有关 FIPS 相容性的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="c2129-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="c2129-111">Windows FIPS 相容性</span><span class="sxs-lookup"><span data-stu-id="c2129-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="c2129-112">针对 FIPS 相容性配置 Windows</span><span class="sxs-lookup"><span data-stu-id="c2129-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="c2129-113">10.2. 联邦信息处理标准（FIPS）</span><span class="sxs-lookup"><span data-stu-id="c2129-113">10.2. FEDERAL INFORMATION PROCESSING STANDARD (FIPS)</span></span>](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
