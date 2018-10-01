---
title: 如何：配置网络跟踪
ms.date: 03/30/2017
helpviewer_keywords:
- formatting [.NET Framework], network tracing
- network tracing, configuring
- level attribute
- app.config files, network tracing
- configuration files [.NET Framework], network tracing
- protocol-level trace output
- application configuration files, network tracing
- sockets, trace output
ms.assetid: 5ef9fe4b-8d3d-490e-9259-1d014b2181af
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 4b8fa55375de5057eca92591cbf4d9da628a3f85
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47193796"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="5c4ed-102">如何：配置网络跟踪</span><span class="sxs-lookup"><span data-stu-id="5c4ed-102">How to: Configure Network Tracing</span></span>
<span data-ttu-id="5c4ed-103">应用程序或计算机配置文件可保存用于确定网络跟踪的格式和内容的设置。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="5c4ed-104">在执行此过程之前，请确保启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="5c4ed-105">有关如何启用跟踪的信息，请参阅[启用网络跟踪](../../../docs/framework/network-programming/enabling-network-tracing.md)。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-105">For information about enabling tracing, see [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md).</span></span>  
  
 <span data-ttu-id="5c4ed-106">计算机配置文件 machine.config 存储在 Windows 安装目录的 %Windir%\Microsoft.NET\Framework 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-106">The computer configuration file, machine.config, is stored in the %Windir%\Microsoft.NET\Framework folder in the directory where Windows was installed.</span></span> <span data-ttu-id="5c4ed-107">安装在计算机上的每个 .NET Framework 版本，在 %Windir%\Microsoft.NET\Framework 下的文件夹中分别有一个单独的 machine.config 文件（例如，C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config 或 C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config）。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-107">There is a separate machine.config file in the folders under %Windir%\Microsoft.NET\Framework for each version of the .NET Framework installed on the computer (for example, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config or C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span></span>  
  
 <span data-ttu-id="5c4ed-108">也可以在应用程序的配置文件中做出这些设置，其优先级别高于计算机配置文件。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-108">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
### <a name="to-configure-network-tracing"></a><span data-ttu-id="5c4ed-109">配置网络跟踪</span><span class="sxs-lookup"><span data-stu-id="5c4ed-109">To configure network tracing</span></span>  
  
-   <span data-ttu-id="5c4ed-110">将下面的代码行添加到相应的配置文件。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-110">Add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="5c4ed-111">这些设置的值和选项已在下表中予以说明。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-111">The values and options for these settings are described in the tables below.</span></span>  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="System.Net" tracemode="includehex" maxdatasize="1024">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Cache">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Http">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Sockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.WebSockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="System.Net" value="Verbose"/>  
          <add name="System.Net.Cache" value="Verbose"/>  
          <add name="System.Net.Http" value="Verbose"/>  
          <add name="System.Net.Sockets" value="Verbose"/>  
          <add name="System.Net.WebSockets" value="Verbose"/>  
        </switches>  
        <sharedListeners>  
          <add name="System.Net"  
            type="System.Diagnostics.TextWriterTraceListener"  
            initializeData="network.log"  
          />  
        </sharedListeners>  
        <trace autoflush="true"/>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
 <span data-ttu-id="5c4ed-112">当你将一个名称添加到 `<switches>` 块后，跟踪输出中将包括来自与该名称相关的一些方法的信息。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-112">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="5c4ed-113">下表对输出进行了说明。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-113">The following table describes the output.</span></span>  
  
|<span data-ttu-id="5c4ed-114">name</span><span class="sxs-lookup"><span data-stu-id="5c4ed-114">Name</span></span>|<span data-ttu-id="5c4ed-115">输出来自</span><span class="sxs-lookup"><span data-stu-id="5c4ed-115">Output from</span></span>|  
|----------|-----------------|  
|`System.Net.Sockets`|<span data-ttu-id="5c4ed-116"><xref:System.Net.Sockets.Socket>、<xref:System.Net.Sockets.TcpListener>、<xref:System.Net.Sockets.TcpClient> 和 <xref:System.Net.Dns> 类的一些公共方法</span><span class="sxs-lookup"><span data-stu-id="5c4ed-116">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes</span></span>|  
|`System.Net`|<span data-ttu-id="5c4ed-117"><xref:System.Net.HttpWebRequest>、<xref:System.Net.HttpWebResponse>、<xref:System.Net.FtpWebRequest> 和 <xref:System.Net.FtpWebResponse> 类的一些公共方法，以及 SSL 调试信息（证书无效、缺少颁发机构列表以及客户端证书错误）。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-117">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors.)</span></span>|  
|`System.Net.HttpListener`|<span data-ttu-id="5c4ed-118"><xref:System.Net.HttpListener>、<xref:System.Net.HttpListenerRequest> 和 <xref:System.Net.HttpListenerResponse> 类的一些公共方法。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-118">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|  
|`System.Net.Cache`|<span data-ttu-id="5c4ed-119">`System.Net.Cache` 中的一些私有方法和内部方法。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-119">Some private and internal methods in `System.Net.Cache`.</span></span>|  
|`System.Net.Http`|<span data-ttu-id="5c4ed-120"><xref:System.Net.Http.HttpClient>、<xref:System.Net.Http.DelegatingHandler>、<xref:System.Net.Http.HttpClientHandler>、<xref:System.Net.Http.HttpMessageHandler>、<xref:System.Net.Http.MessageProcessingHandler> 和 <xref:System.Net.Http.WebRequestHandler> 类的一些公共方法。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-120">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|  
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="5c4ed-121"><xref:System.Net.WebSockets.ClientWebSocket> 和 <xref:System.Net.WebSockets.WebSocket> 类的一些公共方法。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-121">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|  
  
 <span data-ttu-id="5c4ed-122">下表中列出的特性用于配置跟踪输出。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-122">The attributes listed in the following table configure trace output.</span></span>  
  
|<span data-ttu-id="5c4ed-123">特性名</span><span class="sxs-lookup"><span data-stu-id="5c4ed-123">Attribute name</span></span>|<span data-ttu-id="5c4ed-124">特性值</span><span class="sxs-lookup"><span data-stu-id="5c4ed-124">Attribute value</span></span>|  
|--------------------|---------------------|  
|`Value`|<span data-ttu-id="5c4ed-125">必选的 <xref:System.String> 特性。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-125">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="5c4ed-126">设置输出的详细程度。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-126">Sets the verbosity of the output.</span></span> <span data-ttu-id="5c4ed-127">合法值为 `Critical`、`Error`、`Verbose`、`Warning` 和 `Information`。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-127">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /> <span data-ttu-id="5c4ed-128">如此示例所示，此特性必须在 \<switches> 元素的 \<add name> 元素上进行设置。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-128">This attribute must be set on the \<add name> element of the \<switches> element as shown in the example.</span></span> <span data-ttu-id="5c4ed-129">如果此特性是在 \<source> 元素上设置的，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-129">An exception is thrown if this attribute is set on the \<source> element.</span></span>|  
|`maxdatasize`|<span data-ttu-id="5c4ed-130">可选的 <xref:System.Int32> 特性。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-130">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="5c4ed-131">设置每行跟踪中包含的最大网络数据字节数。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-131">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="5c4ed-132">默认值为 1024。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-132">The default value is 1024.</span></span><br /><br /> <span data-ttu-id="5c4ed-133">如此示例所示，此特性必须在 \<source> 元素上进行设置。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-133">This attribute must be set on the \<source> element as shown in the example.</span></span> <span data-ttu-id="5c4ed-134">如果此特性是在 \<switches> 元素下的一个元素上设置的，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-134">An exception is thrown if this attribute is set on an element under the \<switches> element.</span></span>|  
|`Tracemode`|<span data-ttu-id="5c4ed-135">可选的 <xref:System.String> 特性。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-135">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="5c4ed-136">设置为 `includehex` 将会以十六进制和文本格式显示协议跟踪。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-136">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="5c4ed-137">设置为 `protocolonly` 将会仅显示文本。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-137">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="5c4ed-138">默认值为 `includehex`。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-138">The default value is `includehex`.</span></span><br /><br /> <span data-ttu-id="5c4ed-139">如此示例所示，此特性必须在 \<switches> 元素上进行设置。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-139">This attribute must be set on the \<switches> element as shown in the example.</span></span> <span data-ttu-id="5c4ed-140">如果此特性是在 \<source> 元素下的一个元素上设置的，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="5c4ed-140">An exception is thrown if this attribute is set on an element under the \<source> element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c4ed-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c4ed-141">See Also</span></span>  
 [<span data-ttu-id="5c4ed-142">解释网络跟踪</span><span class="sxs-lookup"><span data-stu-id="5c4ed-142">Interpreting Network Tracing</span></span>](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [<span data-ttu-id="5c4ed-143">.NET Framework 中的网络跟踪</span><span class="sxs-lookup"><span data-stu-id="5c4ed-143">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)  
 [<span data-ttu-id="5c4ed-144">启用网络跟踪</span><span class="sxs-lookup"><span data-stu-id="5c4ed-144">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [<span data-ttu-id="5c4ed-145">检测和跟踪简介</span><span class="sxs-lookup"><span data-stu-id="5c4ed-145">Introduction to Instrumentation and Tracing</span></span>](https://msdn.microsoft.com/library/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
