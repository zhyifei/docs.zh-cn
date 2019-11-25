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
ms.openlocfilehash: 06132509860b16d1e22cfdf7e3226c968d16b7cf
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040645"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="c6f2d-102">如何：配置网络跟踪</span><span class="sxs-lookup"><span data-stu-id="c6f2d-102">How to: Configure network tracing</span></span>

<span data-ttu-id="c6f2d-103">应用程序或计算机配置文件可保存用于确定网络跟踪的格式和内容的设置。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="c6f2d-104">在执行此过程之前，请确保启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="c6f2d-105">有关详细信息，请参阅[启用网络跟踪](enabling-network-tracing.md)。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-105">For more information, see [Enable network tracing](enabling-network-tracing.md).</span></span>

<span data-ttu-id="c6f2d-106">计算机配置文件 machine.config  存储在 %windir%\Microsoft.NET\Framework  文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-106">The computer configuration file, *machine.config*, is stored in the *%windir%\Microsoft.NET\Framework* folder.</span></span> <span data-ttu-id="c6f2d-107">安装在计算机上的每个版本的 .NET Framework，在 %windir%\Microsoft.NET\Framework  下的文件夹中分别有一个单独的 machine.config  文件，例如：</span><span class="sxs-lookup"><span data-stu-id="c6f2d-107">There is a separate *machine.config* file in the folders under *%windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer, for example:</span></span>

- <span data-ttu-id="c6f2d-108">C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config </span><span class="sxs-lookup"><span data-stu-id="c6f2d-108">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span></span>
- <span data-ttu-id="c6f2d-109">C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config </span><span class="sxs-lookup"><span data-stu-id="c6f2d-109">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span></span>

<span data-ttu-id="c6f2d-110">也可以在应用程序的配置文件中做出这些设置，其优先级别高于计算机配置文件。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-110">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>

## <a name="configure-network-tracing"></a><span data-ttu-id="c6f2d-111">配置网络跟踪</span><span class="sxs-lookup"><span data-stu-id="c6f2d-111">Configure network tracing</span></span>

<span data-ttu-id="c6f2d-112">要配置网络跟踪，请将下面的行添加到相应的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-112">To configure network tracing, add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="c6f2d-113">这些设置的值和选项已在下表中予以说明。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-113">The values and options for these settings are described in the tables below.</span></span>

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
        traceOutputOptions="ProcessId, DateTime"
      />
    </sharedListeners>
    <trace autoflush="true"/>
  </system.diagnostics>
</configuration>
```

### <a name="trace-output-from-methods"></a><span data-ttu-id="c6f2d-114">跟踪方法的输出</span><span class="sxs-lookup"><span data-stu-id="c6f2d-114">Trace output from methods</span></span>

<span data-ttu-id="c6f2d-115">当你将一个名称添加到 `<switches>` 块后，跟踪输出中将包括来自与该名称相关的一些方法的信息。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-115">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="c6f2d-116">下表对输出进行了说明：</span><span class="sxs-lookup"><span data-stu-id="c6f2d-116">The following table describes the output:</span></span>

|<span data-ttu-id="c6f2d-117">name</span><span class="sxs-lookup"><span data-stu-id="c6f2d-117">Name</span></span>|<span data-ttu-id="c6f2d-118">输出来自</span><span class="sxs-lookup"><span data-stu-id="c6f2d-118">Output from</span></span>|
|----------|-----------------|
|`System.Net.Sockets`|<span data-ttu-id="c6f2d-119"><xref:System.Net.Sockets.Socket>、<xref:System.Net.Sockets.TcpListener>、<xref:System.Net.Sockets.TcpClient> 和 <xref:System.Net.Dns> 类的一些公共方法。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-119">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes.</span></span>|
|`System.Net`|<span data-ttu-id="c6f2d-120"><xref:System.Net.HttpWebRequest>、<xref:System.Net.HttpWebResponse>、<xref:System.Net.FtpWebRequest> 和 <xref:System.Net.FtpWebResponse> 类的一些公共方法，以及 SSL 调试信息（证书无效、缺少颁发机构列表以及客户端证书错误）。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-120">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors).</span></span>|
|`System.Net.HttpListener`|<span data-ttu-id="c6f2d-121"><xref:System.Net.HttpListener>、<xref:System.Net.HttpListenerRequest> 和 <xref:System.Net.HttpListenerResponse> 类的一些公共方法。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-121">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|
|`System.Net.Cache`|<span data-ttu-id="c6f2d-122">`System.Net.Cache` 中的一些私有方法和内部方法。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-122">Some private and internal methods in `System.Net.Cache`.</span></span>|
|`System.Net.Http`|<span data-ttu-id="c6f2d-123"><xref:System.Net.Http.HttpClient>、<xref:System.Net.Http.DelegatingHandler>、<xref:System.Net.Http.HttpClientHandler>、<xref:System.Net.Http.HttpMessageHandler>、<xref:System.Net.Http.MessageProcessingHandler> 和 <xref:System.Net.Http.WebRequestHandler> 类的一些公共方法。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-123">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="c6f2d-124"><xref:System.Net.WebSockets.ClientWebSocket> 和 <xref:System.Net.WebSockets.WebSocket> 类的一些公共方法。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-124">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|

### <a name="trace-output-attributes"></a><span data-ttu-id="c6f2d-125">跟踪输出属性</span><span class="sxs-lookup"><span data-stu-id="c6f2d-125">Trace output attributes</span></span>

<span data-ttu-id="c6f2d-126">下表中列出的属性用于配置跟踪输出：</span><span class="sxs-lookup"><span data-stu-id="c6f2d-126">The attributes listed in the following table configure trace output:</span></span>

|<span data-ttu-id="c6f2d-127">特性名</span><span class="sxs-lookup"><span data-stu-id="c6f2d-127">Attribute name</span></span>|<span data-ttu-id="c6f2d-128">特性值</span><span class="sxs-lookup"><span data-stu-id="c6f2d-128">Attribute value</span></span>|
|--------------------|---------------------|
|`value`|<span data-ttu-id="c6f2d-129">必选的 <xref:System.String> 特性。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-129">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="c6f2d-130">设置输出的详细程度。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-130">Sets the verbosity of the output.</span></span> <span data-ttu-id="c6f2d-131">合法值为 `Critical`、`Error`、`Verbose`、`Warning` 和 `Information`。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-131">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /><span data-ttu-id="c6f2d-132">必须在 switches 元素的 add 元素上设置此属性   。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-132">This attribute must be set on the **add** element of the **switches** element.</span></span> <span data-ttu-id="c6f2d-133">如果在 source 元素上设置此属性，则会引发异常  。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-133">An exception is thrown if this attribute is set on the **source** element.</span></span><br/><br/><span data-ttu-id="c6f2d-134">示例：`<add name="System.Net" value="Verbose"/>`</span><span class="sxs-lookup"><span data-stu-id="c6f2d-134">Example: `<add name="System.Net" value="Verbose"/>`</span></span>|
|`maxdatasize`|<span data-ttu-id="c6f2d-135">可选的 <xref:System.Int32> 特性。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-135">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="c6f2d-136">设置每行跟踪中包含的最大网络数据字节数。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-136">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="c6f2d-137">默认值为 1024。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-137">The default value is 1024.</span></span><br /><br /><span data-ttu-id="c6f2d-138">必须在 source 元素上设置此属性  。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-138">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="c6f2d-139">如果在 switches 元素下的一个元素上设置此属性，则会引发异常  。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-139">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="c6f2d-140">示例：`<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="c6f2d-140">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|
|`tracemode`|<span data-ttu-id="c6f2d-141">可选的 <xref:System.String> 特性。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-141">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="c6f2d-142">设置为 `includehex` 将会以十六进制和文本格式显示协议跟踪。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-142">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="c6f2d-143">设置为 `protocolonly` 将会仅显示文本。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-143">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="c6f2d-144">默认值为 `includehex`。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-144">The default value is `includehex`.</span></span><br /><br /><span data-ttu-id="c6f2d-145">必须在 source 元素上设置此属性  。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-145">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="c6f2d-146">如果在 switches 元素下的一个元素上设置此属性，则会引发异常  。</span><span class="sxs-lookup"><span data-stu-id="c6f2d-146">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="c6f2d-147">示例：`<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="c6f2d-147">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|

## <a name="see-also"></a><span data-ttu-id="c6f2d-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6f2d-148">See also</span></span>

- [<span data-ttu-id="c6f2d-149">解释网络跟踪</span><span class="sxs-lookup"><span data-stu-id="c6f2d-149">Interpreting Network Tracing</span></span>](interpreting-network-tracing.md)
- [<span data-ttu-id="c6f2d-150">.NET Framework 中的网络跟踪</span><span class="sxs-lookup"><span data-stu-id="c6f2d-150">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
- [<span data-ttu-id="c6f2d-151">启用网络跟踪</span><span class="sxs-lookup"><span data-stu-id="c6f2d-151">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="c6f2d-152">跟踪应用程序和在应用程序中插入检测点</span><span class="sxs-lookup"><span data-stu-id="c6f2d-152">Tracing and Instrumenting Applications</span></span>](../debug-trace-profile/tracing-and-instrumenting-applications.md)
