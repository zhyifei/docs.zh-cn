---
title: "如何：修改计算机配置文件以启用 IPv6 支持"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5611b677-b9cc-43b8-a434-60e18d89aada
caps.latest.revision: "18"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 696aeb619f14a5ebe9a760cbd78a0d0fa876edc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-the-computer-configuration-file-to-enable-ipv6-support"></a><span data-ttu-id="98880-102">如何：修改计算机配置文件以启用 IPv6 支持</span><span class="sxs-lookup"><span data-stu-id="98880-102">How to: Modify the Computer Configuration File to Enable IPv6 Support</span></span>
<span data-ttu-id="98880-103">下面的代码示例演示如何修改计算机配置文件 machine.config，以启用 IPv6 支持。</span><span class="sxs-lookup"><span data-stu-id="98880-103">The following code example shows how to modify the computer configuration file, *machine.config*, to enable IPv6 support.</span></span> <span data-ttu-id="98880-104">machine.config 文件存储在 Windows 安装目录的 %Windir%\Microsoft.NET\Framework 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="98880-104">The *machine.config* file is stored in the *%Windir%\Microsoft.NET\Framework* folder in the directory where Windows was installed.</span></span> <span data-ttu-id="98880-105">安装在计算机上的每个 .NET Framework 版本，在 %Windir%\Microsoft.NET\Framework 下的文件夹中分别有一个单独的 machine.config 文件（例如，C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config）。</span><span class="sxs-lookup"><span data-stu-id="98880-105">There is a separate *machine.config* file in the folders under *%Windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer (for example, *C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config*).</span></span>  
  
 <span data-ttu-id="98880-106">也可以在应用程序的配置文件中做出这些设置，其优先级别高于计算机配置文件。</span><span class="sxs-lookup"><span data-stu-id="98880-106">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="98880-107">对于 .NET Framework 1.1 及更早版本，ipv6 enabled 配置开关的值指定 <xref:System.Net.Dns?displayProperty=nameWithType> 类的成员是否返回 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="98880-107">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="98880-108">对于 .NET Framework 2.0 和更高版本，如果 Windows 支持 IPv6，则 <xref:System.Net.Dns?displayProperty=nameWithType> 类的所有成员（例如 <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> 方法）将返回含一个限制的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="98880-108">For .NET Framework version 2.0 and later, if Windows supports IPv6, then all members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="98880-109"><xref:System.Net.Dns?displayProperty=nameWithType> 类的已过时成员（例如，<xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> 方法）将读取并识别配置文件中的值。</span><span class="sxs-lookup"><span data-stu-id="98880-109">Obsolete members of the <xref:System.Net.Dns?displayProperty=nameWithType> class (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98880-110">.NET Framework 2.0 及更高版本默认启用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="98880-110">For .NET Framework version 2.0 and later, IPv6 is enabled by default.</span></span> <span data-ttu-id="98880-111">.NET Framework 1.1 及更低版本默认禁用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="98880-111">For .NET Framework version 1.1 and earlier, IPv6 is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98880-112">示例</span><span class="sxs-lookup"><span data-stu-id="98880-112">Example</span></span>  
  
```xml  
<system.net>  
    …………  
    <settings>  
        …………  
        <ipv6 enabled="true"/>   
    ……………  
    </settings>  
    ………………  
<system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="98880-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98880-113">See Also</span></span>  
 [<span data-ttu-id="98880-114">IPv6 寻址</span><span class="sxs-lookup"><span data-stu-id="98880-114">IPv6 Addressing</span></span>](../../../docs/framework/network-programming/ipv6-addressing.md)  
 [<span data-ttu-id="98880-115">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="98880-115">Network Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="98880-116">\<ipv6> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="98880-116">\<ipv6> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
