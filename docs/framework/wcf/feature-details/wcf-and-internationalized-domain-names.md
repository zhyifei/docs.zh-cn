---
title: WCF 和国际化域名
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: c53c22e388ec352b1275018c0b945c9608565084
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335376"
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="67dc2-102">WCF 和国际化域名</span><span class="sxs-lookup"><span data-stu-id="67dc2-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="67dc2-103">添加了允许使用带有国际化域名 (IDN) 的 WCF 服务的支持。</span><span class="sxs-lookup"><span data-stu-id="67dc2-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="67dc2-104">国际化域名称是包含非 ASCII 字符的域名。</span><span class="sxs-lookup"><span data-stu-id="67dc2-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="67dc2-105">这种支持包括能够承载具有 IDN 名称的 WCF 服务以及 WCF 客户端，以便与具有 IDN 名称的 Web 服务进行对话。</span><span class="sxs-lookup"><span data-stu-id="67dc2-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="67dc2-106">System.Uri 和 IDN</span><span class="sxs-lookup"><span data-stu-id="67dc2-106">System.Uri and IDN</span></span>  
 <xref:System.Uri> <span data-ttu-id="67dc2-107">有两个属性<xref:System.Uri.Host%2A>和<xref:System.Uri.DnsSafeHost%2A>。</span><span class="sxs-lookup"><span data-stu-id="67dc2-107">has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="67dc2-108">根据 IDN 配置设置，这些属性包含 Unicode 或 Punycode 值。</span><span class="sxs-lookup"><span data-stu-id="67dc2-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="67dc2-109">使用下面的 XML 在应用程序的配置文件中启用 IDN</span><span class="sxs-lookup"><span data-stu-id="67dc2-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="67dc2-110">\<Idn > 元素包含已启用的属性可以设置为以下值之一：</span><span class="sxs-lookup"><span data-stu-id="67dc2-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1. <span data-ttu-id="67dc2-111">"None"</span><span class="sxs-lookup"><span data-stu-id="67dc2-111">"None"</span></span>  
  
2. <span data-ttu-id="67dc2-112">"AllExceptIntranet"</span><span class="sxs-lookup"><span data-stu-id="67dc2-112">"AllExceptIntranet"</span></span>  
  
3. <span data-ttu-id="67dc2-113">"全部"</span><span class="sxs-lookup"><span data-stu-id="67dc2-113">"All"</span></span>  
  
 <span data-ttu-id="67dc2-114">在 IDN 设置设为"None"，Uri.Host 或 Uri.DnsSafeHost 不执行任何转换。</span><span class="sxs-lookup"><span data-stu-id="67dc2-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="67dc2-115">在 IDN 设置设为"All"，uri。主机保持 Unicode 和 uri。DnsSafeHost 转换为 Punycode。</span><span class="sxs-lookup"><span data-stu-id="67dc2-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="67dc2-116">在 IDN 设置设为"AllExceptIntranet"，uri。DnsSafeHost 转换为 Punycode 以便用于 internet 地址，并保留 Unicode 以便用于 intranet 地址。</span><span class="sxs-lookup"><span data-stu-id="67dc2-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="67dc2-117">此设置对于正确的 DNS 名称解析十分重要。</span><span class="sxs-lookup"><span data-stu-id="67dc2-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="67dc2-118">请注意，无需为 Windows 8 和更新版本配置此设置。</span><span class="sxs-lookup"><span data-stu-id="67dc2-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="67dc2-119">您应该永远不会使用 Punycode 对地址进行硬代码。</span><span class="sxs-lookup"><span data-stu-id="67dc2-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="67dc2-120">WCF 将会基于您应用的配置设置为您转换它。</span><span class="sxs-lookup"><span data-stu-id="67dc2-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="67dc2-121">将 Unicode 字符添加到 applicationHost.exe.config 时，使用 UTF-8 编码保存文件。</span><span class="sxs-lookup"><span data-stu-id="67dc2-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67dc2-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="67dc2-122">See also</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
