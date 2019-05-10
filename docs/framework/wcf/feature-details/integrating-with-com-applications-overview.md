---
title: COM 应用程序集成概述
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: 2be428f0ae83596a4398fc9830af40d05f6ab191
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638654"
---
# <a name="integrating-with-com-applications-overview"></a><span data-ttu-id="d7a6b-102">COM 应用程序集成概述</span><span class="sxs-lookup"><span data-stu-id="d7a6b-102">Integrating with COM Applications Overview</span></span>
<span data-ttu-id="d7a6b-103">Windows Communication Foundation (WCF) 提供了托管的代码开发人员，使用用于创建连接的应用程序的丰富环境。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-103">Windows Communication Foundation (WCF) provides the managed code developer with a rich environment for creating connected applications.</span></span> <span data-ttu-id="d7a6b-104">但是，如果有大量投入时基于 COM 的非托管代码中，并且不希望迁移，可以仍将 WCF Web 服务直接到现有代码使用 WCF 服务名字对象。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-104">However, if you have a substantial investment in unmanaged COM-based code and do not want to migrate, you can still integrate WCF Web services directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="d7a6b-105">服务标记可以在众多基于 COM 的开发环境（如 Office VBA、Visual Basic 6.0 或 Visual C++ 6.0）中使用。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-105">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7a6b-106">服务标记的所有通信使用 WCF 通信通道。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-106">The service moniker uses a WCF communication channel for all communication.</span></span> <span data-ttu-id="d7a6b-107">用于该通道的安全和标识机制不同于标准 COM 和 DCOM 代理中使用的机制。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-107">The security and identity mechanisms for that channel differ from those used in standard COM and DCOM proxies.</span></span> <span data-ttu-id="d7a6b-108">此外，由于服务标记使用 WCF 通信通道的默认超时时间是一分钟的所有调用。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-108">In addition, because the service moniker uses a WCF communication channel the default timeout period is one minute for all calls.</span></span>  
  
 <span data-ttu-id="d7a6b-109">服务标记用于`GetObject`函数以非托管开发人员提供了强类型化、 特定于 COM 的方法调用 WCF Web 服务。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-109">The service moniker is used with the `GetObject` function to provide the unmanaged developer with a strongly-typed, COM-specific approach for calling WCF Web services.</span></span> <span data-ttu-id="d7a6b-110">这需要本地、 在 WCF Web 服务协定和要使用的绑定的 COM 可见定义。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-110">This requires a local, COM-visible definition of the WCF Web service contract and the binding that is to be used.</span></span> <span data-ttu-id="d7a6b-111">如其他 WCF 客户端，服务标记必须构造到服务的类型化的通道尽管这一通道构造对 COM 程序员在首次方法调用以透明方式发生。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-111">Like other WCF clients, the service moniker must construct a typed channel to the service, though this channel construction occurs transparently to the COM programmer on the first method call.</span></span>  
  
 <span data-ttu-id="d7a6b-112">与其他 WCF 客户端中，使用标记时，应用程序指定地址、 绑定和协定与服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-112">In common with other WCF clients, when using the moniker, applications specify the address, binding and contract to communicate with a service.</span></span> <span data-ttu-id="d7a6b-113">可以采用以下方式之一来指定协定：</span><span class="sxs-lookup"><span data-stu-id="d7a6b-113">The contract can be specified in one of the following ways:</span></span>  
  
- <span data-ttu-id="d7a6b-114">类型化协定 – 该协定在客户端计算机上注册为 COM 可见类型。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-114">Typed contract – the contract is registered as a COM visible type on the client machine.</span></span>  
  
- <span data-ttu-id="d7a6b-115">WSDL 协定 – 该协定以 WSDL 文档的形式提供。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-115">WSDL contract – the contract is supplied in the form of a WSDL document.</span></span>  
  
- <span data-ttu-id="d7a6b-116">MEX 协定 – 在运行时从元数据交换 (MEX) 终结点检索协定。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-116">MEX contract – the contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="parameters-supported-by-the-service-moniker"></a><span data-ttu-id="d7a6b-117">服务标记支持的参数</span><span class="sxs-lookup"><span data-stu-id="d7a6b-117">Parameters Supported by the Service Moniker</span></span>  
 <span data-ttu-id="d7a6b-118">下表显示了服务标记支持的参数。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-118">The following table shows the parameters that are supported by the service moniker.</span></span>  
  
|<span data-ttu-id="d7a6b-119">参数</span><span class="sxs-lookup"><span data-stu-id="d7a6b-119">Parameter</span></span>|<span data-ttu-id="d7a6b-120">描述</span><span class="sxs-lookup"><span data-stu-id="d7a6b-120">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="d7a6b-121">服务的 URL 位置。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-121">URL location of the service.</span></span>|  
|`binding`|<span data-ttu-id="d7a6b-122">应用程序配置中的绑定节名。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-122">Binding section name from the application configuration.</span></span>|  
|`bindingConfiguration`|<span data-ttu-id="d7a6b-123">命名绑定节中的命名绑定实例。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-123">Named binding instance from within the named binding section.</span></span>|  
|`contract`|<span data-ttu-id="d7a6b-124">表示服务协定或协定名称（MEX 中）的接口标识符 (IID)。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-124">Interface identifier (IID) that represents the service contract or the contract name (from MEX).</span></span>|  
|`wsdl`|<span data-ttu-id="d7a6b-125">提供协定定义的替代形式的 WSDL 文档。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-125">WSDL document that provides an alternative form of contract definition.</span></span>|  
|`spnIdentity`|<span data-ttu-id="d7a6b-126">用于与服务通信的服务器主体名称 (SPN) 标识。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-126">Server principal name (SPN) identity to be used to communicate with the service.</span></span>|  
|`upnIdentity`|<span data-ttu-id="d7a6b-127">用于与服务通信的用户主体名称 (UPN) 标识。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-127">User principal name (UPN) identity to be used to communicate with the service.</span></span>|  
|`dnsIdentity`|<span data-ttu-id="d7a6b-128">用于与服务通信的 DNS 标识。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-128">DNS identity to be used to communicate with the service.</span></span>|  
|`mexAddress`|<span data-ttu-id="d7a6b-129">服务的元数据交换 (MEX) 终结点的 URL 位置。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-129">URL location of the Metadata Exchange (MEX) endpoint of the service.</span></span>|  
|`mexBinding`|<span data-ttu-id="d7a6b-130">应用程序配置中用于与 MEX 终结点连接的绑定节名。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-130">Binding section name from the application configuration to connect with the MEX endpoint.</span></span>|  
|`mexBindingConfiguration`|<span data-ttu-id="d7a6b-131">命名绑定节中用于与 MEX 终结点连接的命名绑定实例。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-131">Named binding instance from within the named binding section to connect with the MEX endpoint.</span></span>|  
|`bindingNamespace`|<span data-ttu-id="d7a6b-132">检索的 MEX 中绑定节名的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-132">Namespace of the binding section name from the retrieved MEX.</span></span>|  
|`contractNamespace`|<span data-ttu-id="d7a6b-133">检索的 MEX 中协定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-133">Namespace of the contract from the retrieved MEX.</span></span>|  
|`mexSpnIdentity`|<span data-ttu-id="d7a6b-134">用于与 MEX 终结点通信的服务器主体名称 (SPN) 标识。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-134">Server principal name (SPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexUpnIdentity`|<span data-ttu-id="d7a6b-135">用于与 MEX 终结点通信的用户主体名称 (UPN) 标识。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-135">User principal name (UPN) identity to be used to communicate with the MEX endpoint.</span></span>|  
|`mexDnsIdentity`|<span data-ttu-id="d7a6b-136">用于与 MEX 终结点通信的 DNS 标识。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-136">DNS identity to be used to communicate with the MEX endpoint.</span></span>|  
|`serializer`|<span data-ttu-id="d7a6b-137">指定“xml”或“datacontract”序列化程序的用法。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-137">Specify the use of either the "xml" or "datacontract" serializer.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d7a6b-138">即使与完全基于 COM 的客户端一起使用，服务标记也需要客户端计算机上安装 WCF 和支持的.NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-138">Even when used with entirely COM-based clients, the service moniker requires WCF and the supporting .NET Framework 2.0 to be installed on the client computer.</span></span> <span data-ttu-id="d7a6b-139">使用服务标记的客户端应用程序加载 .NET Framework 运行时的适当版本也很关键。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-139">It is also critical that client applications that use the service moniker load the appropriate version of the .NET Framework runtime.</span></span> <span data-ttu-id="d7a6b-140">在 Office 应用程序内使用标记时，可能需要一个配置文件以确保加载正确的 Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="d7a6b-140">When using the moniker within Office applications, a configuration file may be required to ensure that the correct framework version is loaded.</span></span> <span data-ttu-id="d7a6b-141">例如，使用 Excel 时，以下文本应放在与 Excel.exe 文件位于同一目录中的名为 Excel.exe.config 的文件中：</span><span class="sxs-lookup"><span data-stu-id="d7a6b-141">For example, with Excel, the following text should be placed in a file called Excel.exe.config in the same directory as the Excel.exe file:</span></span>  
>   
>  `<?xml version="1.0" encoding="utf-8"?>`  
>   
>  <span data-ttu-id="d7a6b-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span><span class="sxs-lookup"><span data-stu-id="d7a6b-142">`<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`</span></span>  
>   
>  `<startup>`  
>   
>  `<requiredRuntime version="v2.0.50727" />`  
>   
>  `</startup>`  
>   
>  `</configuration>`  
  
## <a name="see-also"></a><span data-ttu-id="d7a6b-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7a6b-143">See also</span></span>

- [<span data-ttu-id="d7a6b-144">如何：注册并配置服务名字对象</span><span class="sxs-lookup"><span data-stu-id="d7a6b-144">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
