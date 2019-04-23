---
title: <messageLogging>
ms.date: 03/30/2017
ms.assetid: 1d06a7e6-9633-4a12-8c5d-123adbbc19c5
ms.openlocfilehash: 70fb2df1d37af23d9ec19932806989ce3329bf3c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191563"
---
# <a name="messagelogging"></a><span data-ttu-id="c0f7a-101">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="c0f7a-101">\<messageLogging></span></span>
<span data-ttu-id="c0f7a-102">该元素定义 Windows Communication Foundation (WCF) 的消息日志记录功能的设置。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-102">This element defines the settings for the message-logging capabilities of Windows Communication Foundation (WCF).</span></span>  
  
 <span data-ttu-id="c0f7a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c0f7a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c0f7a-104">\<diagnostic></span><span class="sxs-lookup"><span data-stu-id="c0f7a-104">\<diagnostic></span></span>  
<span data-ttu-id="c0f7a-105">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="c0f7a-105">\<messageLogging></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0f7a-106">语法</span><span class="sxs-lookup"><span data-stu-id="c0f7a-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
      <filters>
        <clear />
      </filters>
    </messageLogging>
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0f7a-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c0f7a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c0f7a-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0f7a-109">特性</span><span class="sxs-lookup"><span data-stu-id="c0f7a-109">Attributes</span></span>  
  
|<span data-ttu-id="c0f7a-110">特性</span><span class="sxs-lookup"><span data-stu-id="c0f7a-110">Attribute</span></span>|<span data-ttu-id="c0f7a-111">描述</span><span class="sxs-lookup"><span data-stu-id="c0f7a-111">Description</span></span>|  
|---------------|-----------------|  
|`logEntireMessage`|<span data-ttu-id="c0f7a-112">一个布尔值，指定是否记录整个消息（消息头和正文）。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-112">A Boolean value that specifies whether the entire message (message header and body) is logged.</span></span> <span data-ttu-id="c0f7a-113">默认值为 `false`，这意味着仅记录消息头。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-113">The default is `false`, which means that only the message header is logged.</span></span> <span data-ttu-id="c0f7a-114">此设置会影响所有消息日志记录级别（服务、传输和格式不正确）。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-114">This setting affects all message logging levels (service, transport, and malformed).</span></span>|  
|`logMalformedMessages`|<span data-ttu-id="c0f7a-115">一个布尔值，指定是否记录格式不正确的消息。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-115">A Boolean value that specifies whether malformed messages are logged.</span></span> <span data-ttu-id="c0f7a-116">格式不正确的消息将不计入 `maxMessagesToLog`。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-116">Malformed messages do not count toward the `maxMessagesToLog`.</span></span> <span data-ttu-id="c0f7a-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-117">The default is `false`.</span></span>|  
|`logMessagesAtServiceLevel`|<span data-ttu-id="c0f7a-118">一个布尔值，指定是否在服务级别跟踪消息（在与加密和传输有关的转换之前）。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-118">A Boolean value that specifies whether messages are traced at the service level (before encryption- and transport-related transforms).</span></span> <span data-ttu-id="c0f7a-119">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-119">The default is `false`.</span></span>|  
|`logMessagesAtTransportLevel`|<span data-ttu-id="c0f7a-120">一个布尔值，指定是否在传输级别跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-120">A Boolean value that specifies whether messages are traced at the transport level.</span></span> <span data-ttu-id="c0f7a-121">配置文件中指定的所有筛选器都会应用，但仅跟踪与这些筛选器相匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-121">Any filters specified in the config file are applied, and only messages that match the filters are traced.</span></span> <span data-ttu-id="c0f7a-122">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-122">The default is `false`.</span></span>|  
|`maxMessagesToLog`|<span data-ttu-id="c0f7a-123">一个正整数，指定要记录的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-123">A positive integer that specifies the maximum number of messages to log.</span></span> <span data-ttu-id="c0f7a-124">默认值为 1000。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-124">The default is 1000.</span></span>|  
|`maxSizeOfMessageToLog`|<span data-ttu-id="c0f7a-125">一个正整数，指定要记录的最大消息大小（字节）。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-125">A positive integer that specifies the maximum size, in bytes, of a message to log.</span></span> <span data-ttu-id="c0f7a-126">大小超出限制的消息将不会被记录。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-126">Messages larger than the limit will not be logged.</span></span> <span data-ttu-id="c0f7a-127">此设置会影响所有跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-127">This setting affects all trace levels.</span></span> <span data-ttu-id="c0f7a-128">默认值为 262144 (0x4000)。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-128">The default is 262144(0x4000).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0f7a-129">子元素</span><span class="sxs-lookup"><span data-stu-id="c0f7a-129">Child Elements</span></span>  
  
|<span data-ttu-id="c0f7a-130">元素</span><span class="sxs-lookup"><span data-stu-id="c0f7a-130">Element</span></span>|<span data-ttu-id="c0f7a-131">描述</span><span class="sxs-lookup"><span data-stu-id="c0f7a-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0f7a-132">筛选器</span><span class="sxs-lookup"><span data-stu-id="c0f7a-132">filters</span></span>|<span data-ttu-id="c0f7a-133">`filters` 元素包含 XPath 筛选器集合。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-133">The `filters` element holds a collection of XPath filters.</span></span> <span data-ttu-id="c0f7a-134">启用传输消息日志记录后（`logMessagesAtTransportLevel` 为 `true`），只有与筛选器匹配的消息才会记录下来。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-134">When transport message logging is enabled (`logMessagesAtTransportLevel` is `true`), only messages matching the filters will be logged.</span></span><br /><br /> <span data-ttu-id="c0f7a-135">筛选器仅应用于传输层。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-135">Filters are applied only at the transport layer.</span></span> <span data-ttu-id="c0f7a-136">筛选器不影响服务级别和格式不正确的消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-136">Service level and malformed message logging are not affected by filters.</span></span><br /><br /> <span data-ttu-id="c0f7a-137">此元素唯一的属性为 `filter` XpathFilter。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-137">The only attribute for this element, `filter`, is an XpathFilter.</span></span><br /><br /> `<filters>     <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">/soap:Envelope</add> </filters>`|  
  
### <a name="parent-elements"></a><span data-ttu-id="c0f7a-138">父元素</span><span class="sxs-lookup"><span data-stu-id="c0f7a-138">Parent Elements</span></span>  
  
|<span data-ttu-id="c0f7a-139">元素</span><span class="sxs-lookup"><span data-stu-id="c0f7a-139">Element</span></span>|<span data-ttu-id="c0f7a-140">描述</span><span class="sxs-lookup"><span data-stu-id="c0f7a-140">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0f7a-141">诊断</span><span class="sxs-lookup"><span data-stu-id="c0f7a-141">diagnostics</span></span>|<span data-ttu-id="c0f7a-142">定义管理员运行时检查和控制的 WCF 设置。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-142">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0f7a-143">备注</span><span class="sxs-lookup"><span data-stu-id="c0f7a-143">Remarks</span></span>  
 <span data-ttu-id="c0f7a-144">将在堆栈中以下三个不同级别记录消息：服务、传输和格式不正确。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-144">Messages are logged at three different levels in the stack: service, transport, and malformed.</span></span> <span data-ttu-id="c0f7a-145">可以单独激活每个级别。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-145">Each level can be activated separately.</span></span>  
  
 <span data-ttu-id="c0f7a-146">可添加 XPath 筛选器以记录传输和服务级别的特定消息。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-146">XPath filters can be added to log specific messages at the transport and service levels.</span></span> <span data-ttu-id="c0f7a-147">如果未定义任何筛选器，则记录所有消息。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-147">If no filters are defined, all messages are logged.</span></span> <span data-ttu-id="c0f7a-148">筛选器仅应用于消息的标头。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-148">Filters are applied only to the headers of the message.</span></span> <span data-ttu-id="c0f7a-149">正文会被忽略。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-149">The body is ignored.</span></span> <span data-ttu-id="c0f7a-150">WCF 将忽略消息正文，以便提高性能。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-150">WCF ignores the message body to improve performance.</span></span> <span data-ttu-id="c0f7a-151">如果要根据正文内容进行筛选，可以创建一个自定义侦听器，并采用具有相应功能的筛选器。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-151">If you want to filter based on the content of the body, you can create a custom listener with a filter that does so.</span></span>  
  
 <span data-ttu-id="c0f7a-152">您需要创建一个跟踪侦听器以激活消息跟踪。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-152">You need to create a trace listener to activate message tracing.</span></span> <span data-ttu-id="c0f7a-153">侦听器本身可以是使用 <xref:System.Diagnostics> 跟踪体系结构的任何侦听器。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-153">The listener itself can be any listener that works with the <xref:System.Diagnostics> tracing architecture.</span></span> <span data-ttu-id="c0f7a-154">下面的示例演示如何创建此类侦听器。</span><span class="sxs-lookup"><span data-stu-id="c0f7a-154">The following example demonstrates how to create such a listener.</span></span>  
  
```xml  
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel"
            switchValue="Verbose">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="ServiceModel Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
        <clear />
        <add type="System.Diagnostics.DefaultTraceListener"
             name="Default"
             traceOutputOptions="None" />
        <add name="MessageLogging Listener"
             traceOutputOptions="None" />
      </listeners>
    </source>
  </sources>
  <sharedListeners>
    <add initializeData="C:\ItProTools\TraceLog.xml"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="ServiceModel Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
    <add initializeData="C:\ItProTools\MessageLog.log"
         type="System.Diagnostics.XmlWriterTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         name="MessageLogging Listener"
         traceOutputOptions="LogicalOperationStack, DateTime, Timestamp, ProcessId, ThreadId, Callstack" />
  </sharedListeners>
</system.diagnostics>
```  
  
## <a name="example"></a><span data-ttu-id="c0f7a-155">示例</span><span class="sxs-lookup"><span data-stu-id="c0f7a-155">Example</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="42"
                maxSizeOfMessageToLog="42">
  <filters>
    <clear />
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a><span data-ttu-id="c0f7a-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0f7a-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- [<span data-ttu-id="c0f7a-157">配置消息日志记录</span><span class="sxs-lookup"><span data-stu-id="c0f7a-157">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)
