---
title: 缓解：X509CertificateClaimSet.FindClaims 方法
ms.date: 03/30/2017
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
ms.openlocfilehash: 0b306960c4f11bb6f54aecaeb13297e7725e16a8
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102640"
---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a><span data-ttu-id="ecf83-102">缓解：X509CertificateClaimSet.FindClaims 方法</span><span class="sxs-lookup"><span data-stu-id="ecf83-102">Mitigation: X509CertificateClaimSet.FindClaims Method</span></span>

<span data-ttu-id="ecf83-103">从面向 .NET Framework 4.6.1 的应用开始，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 方法尝试将 `claimType` 参数与其 SAN 字段中的所有 DNS 条目进行匹配。</span><span class="sxs-lookup"><span data-stu-id="ecf83-103">Starting with apps that target .NET Framework 4.6.1, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method will attempt to match the `claimType` argument with all the DNS entries in its SAN field.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="ecf83-104">影响</span><span class="sxs-lookup"><span data-stu-id="ecf83-104">Impact</span></span>  
 <span data-ttu-id="ecf83-105">此更改仅影响面向从 .NET Framework 4.6.1 开始的 .NET Framework 版本的应用。</span><span class="sxs-lookup"><span data-stu-id="ecf83-105">This change only affects apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>  
  
 <span data-ttu-id="ecf83-106">对于面向 .NET Framework 先前版本的应用，<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 方法尝试仅将 `claimType` 参数与最后一个 DNS 条目进行匹配。</span><span class="sxs-lookup"><span data-stu-id="ecf83-106">For apps that target previous versions of the .NET Framework, the <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> method attempts to match the `claimType` argument only with the last  DNS entry.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="ecf83-107">缓解</span><span class="sxs-lookup"><span data-stu-id="ecf83-107">Mitigation</span></span>  
 <span data-ttu-id="ecf83-108">如果无需进行此更改，则面向从 .NET Framework 4.6.1 开始的 .NET Framework 版本的应用可通过将以下配置设置添加到应用配置文件的 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 部分，来选择放弃更改：</span><span class="sxs-lookup"><span data-stu-id="ecf83-108">If this change is undesirable, apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1 can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />
</runtime>  
```  
  
 <span data-ttu-id="ecf83-109">此外，面向 .NET Framework 以前版本但在 .NET Framework 4.6.1 或更高版本下运行的应用可通过将以下配置设置添加到应用配置文件的 [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) 部分，来选择实现此行为：</span><span class="sxs-lookup"><span data-stu-id="ecf83-109">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ecf83-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecf83-110">See also</span></span>

- [<span data-ttu-id="ecf83-111">应用程序兼容性</span><span class="sxs-lookup"><span data-stu-id="ecf83-111">Application compatibility</span></span>](application-compatibility.md)
