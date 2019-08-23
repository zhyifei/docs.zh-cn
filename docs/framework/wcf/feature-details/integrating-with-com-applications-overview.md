---
title: COM 应用程序集成概述
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: 6e6ff29e7d292a291c2cb4984a80c5a0927f18d2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934974"
---
# <a name="integrating-with-com-applications-overview"></a><span data-ttu-id="10370-102">COM 应用程序集成概述</span><span class="sxs-lookup"><span data-stu-id="10370-102">Integrating with COM Applications Overview</span></span>
<span data-ttu-id="10370-103">Windows Communication Foundation (WCF) 为托管代码开发人员提供了一个用于创建连接的应用程序的丰富环境。</span><span class="sxs-lookup"><span data-stu-id="10370-103">Windows Communication Foundation (WCF) provides the managed code developer with a rich environment for creating connected applications.</span></span> <span data-ttu-id="10370-104">但是, 如果你对基于 COM 的非托管代码进行了大量投资并且不想迁移, 则仍可以使用 WCF 服务名字对象将 WCF Web 服务直接集成到现有代码中。</span><span class="sxs-lookup"><span data-stu-id="10370-104">However, if you have a substantial investment in unmanaged COM-based code and do not want to migrate, you can still integrate WCF Web services directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="10370-105">服务标记可以在众多基于 COM 的开发环境（如 Office VBA、Visual Basic 6.0 或 Visual C++ 6.0）中使用。</span><span class="sxs-lookup"><span data-stu-id="10370-105">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10370-106">服务标记使用 WCF 信道来进行所有通信。</span><span class="sxs-lookup"><span data-stu-id="10370-106">The service moniker uses a WCF communication channel for all communication.</span></span> <span data-ttu-id="10370-107">用于该通道的安全和标识机制不同于标准 COM 和 DCOM 代理中使用的机制。</span><span class="sxs-lookup"><span data-stu-id="10370-107">The security and identity mechanisms for that channel differ from those used in standard COM and DCOM proxies.</span></span> <span data-ttu-id="10370-108">此外, 由于服务标记使用 WCF 信道, 因此所有调用的默认超时期限为一分钟。</span><span class="sxs-lookup"><span data-stu-id="10370-108">In addition, because the service moniker uses a WCF communication channel the default timeout period is one minute for all calls.</span></span>  
  
 <span data-ttu-id="10370-109">服务标记与`GetObject`函数结合使用, 为非托管开发人员提供强类型的、特定于 COM 的方法来调用 WCF Web 服务。</span><span class="sxs-lookup"><span data-stu-id="10370-109">The service moniker is used with the `GetObject` function to provide the unmanaged developer with a strongly-typed, COM-specific approach for calling WCF Web services.</span></span> <span data-ttu-id="10370-110">这需要 WCF Web 服务协定的本地、COM 可见的定义以及要使用的绑定。</span><span class="sxs-lookup"><span data-stu-id="10370-110">This requires a local, COM-visible definition of the WCF Web service contract and the binding that is to be used.</span></span> <span data-ttu-id="10370-111">与其他 WCF 客户端一样, 服务标记必须构造一个到服务的类型化通道, 但对于第一个方法调用中的 COM 程序员, 此通道构造是透明的。</span><span class="sxs-lookup"><span data-stu-id="10370-111">Like other WCF clients, the service moniker must construct a typed channel to the service, though this channel construction occurs transparently to the COM programmer on the first method call.</span></span>  
  
 <span data-ttu-id="10370-112">与其他 WCF 客户端一样, 在使用名字对象时, 应用程序会指定地址、绑定和协定, 以与服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="10370-112">In common with other WCF clients, when using the moniker, applications specify the address, binding and contract to communicate with a service.</span></span> <span data-ttu-id="10370-113">可以采用以下方式之一来指定协定：</span><span class="sxs-lookup"><span data-stu-id="10370-113">The contract can be specified in one of the following ways:</span></span>  
  
- <span data-ttu-id="10370-114">类型化协定 – 该协定在客户端计算机上注册为 COM 可见类型。</span><span class="sxs-lookup"><span data-stu-id="10370-114">Typed contract – the contract is registered as a COM visible type on the client machine.</span></span>  
  
- <span data-ttu-id="10370-115">WSDL 协定 – 该协定以 WSDL 文档的形式提供。</span><span class="sxs-lookup"><span data-stu-id="10370-115">WSDL contract – the contract is supplied in the form of a WSDL document.</span></span>  
  
- <span data-ttu-id="10370-116">MEX 协定 – 在运行时从元数据交换 (MEX) 终结点检索协定。</span><span class="sxs-lookup"><span data-stu-id="10370-116">MEX contract – the contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="parameters-supported-by-the-service-moniker"></a><span data-ttu-id="10370-117">服务标记支持的参数</span><span class="sxs-lookup"><span data-stu-id="10370-117">Parameters Supported by the Service Moniker</span></span>  
 <span data-ttu-id="10370-118">下表显示了服务标记支持的参数。</span><span class="sxs-lookup"><span data-stu-id="10370-118">The following table shows the parameters that are supported by the service moniker.</span></span>  
  
|<span data-ttu-id="10370-119">参数</span><span class="sxs-lookup"><span data-stu-id="10370-119">Parameter</span></span>|<span data-ttu-id="10370-120">描述</span><span class="sxs-lookup"><span data-stu-id="10370-120">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="10370-121">服务的 URL 位置。</span><span class="sxs-lookup"><span data-stu-id="10370-121">URL location of the service.</span></span>|  
|`binding`|<span data-ttu-id="10370-122">应用程序配置中的绑定节名。</span><span class="sxs-lookup"><span data-stu-id="10370-122">Binding section name from the application configuration.</span></span>|  
|`bindingConfiguration`|<span data-ttu-id="10370-123">命名绑定节中的命名绑定实例。</span><span class="sxs-lookup"><span data-stu-id="10370-123">Named binding instance from within the named binding section.</span></span>|  
|`contract`|<span data-ttu-id="10370-124">表示服务协定或协定名称（MEX 中）的接口标识符 (IID)。</span><span class="sxs-lookup"><span data-stu-id="10370-124">Interface identifier (IID) that represents the service contract or the contract name (from MEX).</span></span>|  
|`wsdl`|<span data-ttu-id="10370-125">提供协定定义的替代形式的 WSDL 文档。</span><span class="sxs-lookup"><span data-stu-id="10370-125">WSDL document that provides an alternative form of contract definition.</span></span>|  
|`spnIdentity`|<span data-ttu-id="10370-126">用于与服务通信的服务器主体名称 (SPN) 标识。</span><span class="sxs-lookup"><span data-stu-id="10370-126">Server principal name (SPN) identity to be used to communicate with the service.</span></span>|  
|`upnIdentity`|<span data-ttu-id="10370-127">用于与服务通信的用户主体名称 (UPN) 标识。</span><span class="sxs-lookup"><span data-stu-id="10370-127">User principal name (UPN) identity to be used to communicate with the service.</span></span>|  
|`dnsIdentity`|<span data-ttu-id="10370-128">用于与服务通信的 DNS 标识。</span><span class="sxs-lookup"><span data-stu-id="10370-128">DNS identity to be used to communicate with the service.</span></span>|  
|`mexAddress`|<span data-ttu-id="10370-129">服务的元数据交换 (MEX) 终结点的 URL 位置。</span><span class="sxs-lookup"><span data-stu-id="10370-129">URL location of the Metadata Exchange (MEX) endpoint of the service.</span></span>|  
|`mexBinding`|<span data-ttu-id="10370-130">应用程序配置中用于与 MEX 终结点连接的绑定节名。</span><span class="sxs-lookup"><span data-stu-id="10370-130">Binding section name from the application configuration to connect with the MEX endpoint.</span></span>|  
|`mexBindingConfiguration`|<span data-ttu-id="10370-131">命名绑定节中用于与 MEX 终结点连接的命名绑定实例。</span><span class="sxs-lookup"><span data-stu-id="10370-131">Named binding instance from within the named binding section to connect with the MEX endpoint.</span></span>|  
|`bindingNamespace`|<span data-ttu-id="10370-132">检索的 MEX 中绑定节名的命名空间。</span><span class="sxs-lookup"><span data-stu-id="10370-132">Namespace of the binding section name from the retrieved MEX.</span></span>|  
|`contractNamespace`|<span data-ttu-id="10370-133">检索的 MEX 中协定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="10370-133">Namespace of the contract from the retrieved MEX.</span></span>|  
|`mexSpnIdentity`|<span data-ttu-id="10370-134">用于与 MEX 终结点通信的服务器主体名称 (SPN) 标识。</span><span class="sxs-lookup"><span data-stu-id="10370-134">Server principal name (SPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexUpnIdentity`|<span data-ttu-id="10370-135">用于与 MEX 终结点通信的用户主体名称 (UPN) 标识。</span><span class="sxs-lookup"><span data-stu-id="10370-135">User principal name (UPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexDnsIdentity`|<span data-ttu-id="10370-136">用于与 MEX 终结点通信的 DNS 标识。</span><span class="sxs-lookup"><span data-stu-id="10370-136">DNS identity to be used to communicate with the MEX endpoint.</span></span>|  
|`serializer`|<span data-ttu-id="10370-137">指定“xml”或“datacontract”序列化程序的用法。</span><span class="sxs-lookup"><span data-stu-id="10370-137">Specify the use of either the "xml" or "datacontract" serializer.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="10370-138">即使与完全基于 COM 的客户端一起使用, 服务标记也要求在客户端计算机上安装 WCF 和支持的 .NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="10370-138">Even when used with entirely COM-based clients, the service moniker requires WCF and the supporting .NET Framework 2.0 to be installed on the client computer.</span></span> <span data-ttu-id="10370-139">使用服务标记的客户端应用程序加载 .NET Framework 运行时的适当版本也很关键。</span><span class="sxs-lookup"><span data-stu-id="10370-139">It is also critical that client applications that use the service moniker load the appropriate version of the .NET Framework runtime.</span></span> <span data-ttu-id="10370-140">在 Office 应用程序内使用标记时，可能需要一个配置文件以确保加载正确的 Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="10370-140">When using the moniker within Office applications, a configuration file may be required to ensure that the correct framework version is loaded.</span></span> <span data-ttu-id="10370-141">例如，使用 Excel 时，以下文本应放在与 Excel.exe 文件位于同一目录中的名为 Excel.exe.config 的文件中：</span><span class="sxs-lookup"><span data-stu-id="10370-141">For example, with Excel, the following text should be placed in a file called Excel.exe.config in the same directory as the Excel.exe file:</span></span>  
>   
>  `<?xml version="1.0" encoding="utf-8"?>`  
>   
>  <span data-ttu-id="10370-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span><span class="sxs-lookup"><span data-stu-id="10370-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span></span>  
>   
>  `<startup>`  
>   
>  `<requiredRuntime version="v2.0.50727" />`  
>   
>  `</startup>`  
>   
>  `</configuration>`  
  
## <a name="see-also"></a><span data-ttu-id="10370-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="10370-143">See also</span></span>

- [<span data-ttu-id="10370-144">如何：注册和配置服务标记</span><span class="sxs-lookup"><span data-stu-id="10370-144">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
