---
title: 使用匿名客户端的 WCF 传输安全性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 20d7e59ba2b4b9dedc0b0daff1c1aa9c5210e61b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932936"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="8fec4-102">匿名客户端使用的传输安全性</span><span class="sxs-lookup"><span data-stu-id="8fec4-102">Transport security with an anonymous client</span></span>

<span data-ttu-id="8fec4-103">此 Windows Communication Foundation (WCF) 方案中使用传输安全 (HTTPS) 确保保密性和完整性。</span><span class="sxs-lookup"><span data-stu-id="8fec4-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="8fec4-104">必须使用安全套接字层 (SSL) 证书对服务器进行身份验证，并且客户端必须信任服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="8fec4-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="8fec4-105">客户端不通过任何机制进行身份验证，因此是匿名的。</span><span class="sxs-lookup"><span data-stu-id="8fec4-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="8fec4-106">示例应用程序，请参阅[WS 传输安全性](../samples/ws-transport-security.md)。</span><span class="sxs-lookup"><span data-stu-id="8fec4-106">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="8fec4-107">有关传输安全性的详细信息，请参阅[传输安全概述](transport-security-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8fec4-107">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="8fec4-108">有关与服务使用的证书的详细信息，请参阅[Working with Certificates](working-with-certificates.md)和[如何：使用 SSL 证书配置端口](how-to-configure-a-port-with-an-ssl-certificate.md)。</span><span class="sxs-lookup"><span data-stu-id="8fec4-108">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![对匿名客户端使用传输安全性](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="8fec4-110">特征</span><span class="sxs-lookup"><span data-stu-id="8fec4-110">Characteristic</span></span>|<span data-ttu-id="8fec4-111">描述</span><span class="sxs-lookup"><span data-stu-id="8fec4-111">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="8fec4-112">安全模式</span><span class="sxs-lookup"><span data-stu-id="8fec4-112">Security Mode</span></span>|<span data-ttu-id="8fec4-113">传输</span><span class="sxs-lookup"><span data-stu-id="8fec4-113">Transport</span></span>|
|<span data-ttu-id="8fec4-114">互操作性</span><span class="sxs-lookup"><span data-stu-id="8fec4-114">Interoperability</span></span>|<span data-ttu-id="8fec4-115">与现有 Web 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="8fec4-115">With existing Web services and clients</span></span>|
|<span data-ttu-id="8fec4-116">身份验证（服务器）</span><span class="sxs-lookup"><span data-stu-id="8fec4-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="8fec4-117">身份验证（客户端）</span><span class="sxs-lookup"><span data-stu-id="8fec4-117">Authentication (Client)</span></span>|<span data-ttu-id="8fec4-118">是</span><span class="sxs-lookup"><span data-stu-id="8fec4-118">Yes</span></span><br /><br /> <span data-ttu-id="8fec4-119">应用程序级别 （无 WCF 支持）</span><span class="sxs-lookup"><span data-stu-id="8fec4-119">Application level (no WCF support)</span></span>|
|<span data-ttu-id="8fec4-120">完整性</span><span class="sxs-lookup"><span data-stu-id="8fec4-120">Integrity</span></span>|<span data-ttu-id="8fec4-121">是</span><span class="sxs-lookup"><span data-stu-id="8fec4-121">Yes</span></span>|
|<span data-ttu-id="8fec4-122">保密性</span><span class="sxs-lookup"><span data-stu-id="8fec4-122">Confidentiality</span></span>|<span data-ttu-id="8fec4-123">是</span><span class="sxs-lookup"><span data-stu-id="8fec4-123">Yes</span></span>|
|<span data-ttu-id="8fec4-124">传输</span><span class="sxs-lookup"><span data-stu-id="8fec4-124">Transport</span></span>|<span data-ttu-id="8fec4-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="8fec4-125">HTTPS</span></span>|
|<span data-ttu-id="8fec4-126">绑定</span><span class="sxs-lookup"><span data-stu-id="8fec4-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="8fec4-127">服务</span><span class="sxs-lookup"><span data-stu-id="8fec4-127">Service</span></span>

<span data-ttu-id="8fec4-128">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="8fec4-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="8fec4-129">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8fec4-129">Do one of the following:</span></span>

- <span data-ttu-id="8fec4-130">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="8fec4-130">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="8fec4-131">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="8fec4-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="8fec4-132">代码</span><span class="sxs-lookup"><span data-stu-id="8fec4-132">Code</span></span>

<span data-ttu-id="8fec4-133">下面的代码演示如何使用传输安全创建终结点：</span><span class="sxs-lookup"><span data-stu-id="8fec4-133">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="8fec4-134">配置</span><span class="sxs-lookup"><span data-stu-id="8fec4-134">Configuration</span></span>

<span data-ttu-id="8fec4-135">下面的代码使用配置设置相同的终结点。</span><span class="sxs-lookup"><span data-stu-id="8fec4-135">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="8fec4-136">客户端不通过任何机制进行身份验证，因此是匿名的。</span><span class="sxs-lookup"><span data-stu-id="8fec4-136">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="SecuredByTransportEndpoint"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator">
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a><span data-ttu-id="8fec4-137">客户端</span><span class="sxs-lookup"><span data-stu-id="8fec4-137">Client</span></span>

<span data-ttu-id="8fec4-138">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="8fec4-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="8fec4-139">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="8fec4-139">Do one of the following:</span></span>

- <span data-ttu-id="8fec4-140">使用代码（和客户端代码）创建独立客户端。</span><span class="sxs-lookup"><span data-stu-id="8fec4-140">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="8fec4-141">创建不定义任何终结点地址的客户端。</span><span class="sxs-lookup"><span data-stu-id="8fec4-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="8fec4-142">而使用将配置名称作为自变量的客户端构造函数。</span><span class="sxs-lookup"><span data-stu-id="8fec4-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="8fec4-143">例如：</span><span class="sxs-lookup"><span data-stu-id="8fec4-143">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="8fec4-144">代码</span><span class="sxs-lookup"><span data-stu-id="8fec4-144">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="8fec4-145">配置</span><span class="sxs-lookup"><span data-stu-id="8fec4-145">Configuration</span></span>

<span data-ttu-id="8fec4-146">下面的配置可代替代码用于设置服务。</span><span class="sxs-lookup"><span data-stu-id="8fec4-146">The following configuration can be used instead of the code to set up the service.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="8fec4-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fec4-147">See also</span></span>

- [<span data-ttu-id="8fec4-148">安全性概述</span><span class="sxs-lookup"><span data-stu-id="8fec4-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="8fec4-149">WS 传输安全性</span><span class="sxs-lookup"><span data-stu-id="8fec4-149">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="8fec4-150">传输安全性概述</span><span class="sxs-lookup"><span data-stu-id="8fec4-150">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="8fec4-151">[Windows Server App Fabric 的安全模型](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="8fec4-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>