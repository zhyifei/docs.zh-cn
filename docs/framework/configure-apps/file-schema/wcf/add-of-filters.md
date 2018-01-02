---
title: "&lt;filters&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1ca0d5ae73d01e5bbb719f7bcc9a3f5a19fc291
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltfiltersgt"></a><span data-ttu-id="77eea-102">&lt;filters&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="77eea-102">&lt;add&gt; of &lt;filters&gt;</span></span>
<span data-ttu-id="77eea-103">一个 XPath 筛选器，用于指定要记录的消息的种类。</span><span class="sxs-lookup"><span data-stu-id="77eea-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
 <span data-ttu-id="77eea-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="77eea-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="77eea-105">\<诊断 ></span><span class="sxs-lookup"><span data-stu-id="77eea-105">\<diagnostic></span></span>  
<span data-ttu-id="77eea-106">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="77eea-106">\<messageLogging></span></span>  
<span data-ttu-id="77eea-107">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="77eea-107">\<filters></span></span>  
<span data-ttu-id="77eea-108">\<add></span><span class="sxs-lookup"><span data-stu-id="77eea-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77eea-109">语法</span><span class="sxs-lookup"><span data-stu-id="77eea-109">Syntax</span></span>  
  
```xml  
<filters>  
   <add filter="String"/>  
</filters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77eea-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="77eea-110">Attributes and Elements</span></span>  
 <span data-ttu-id="77eea-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="77eea-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77eea-112">特性</span><span class="sxs-lookup"><span data-stu-id="77eea-112">Attributes</span></span>  
  
|<span data-ttu-id="77eea-113">特性</span><span class="sxs-lookup"><span data-stu-id="77eea-113">Attribute</span></span>|<span data-ttu-id="77eea-114">描述</span><span class="sxs-lookup"><span data-stu-id="77eea-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77eea-115">筛选器</span><span class="sxs-lookup"><span data-stu-id="77eea-115">filter</span></span>|<span data-ttu-id="77eea-116">一个字符串，用于指定由 XPath 1.0 表达式定义的 XML 文档的查询。</span><span class="sxs-lookup"><span data-stu-id="77eea-116">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="77eea-117">有关详细信息，请参阅<xref:System.ServiceModel.Dispatcher.XPathMessageFilter>。</span><span class="sxs-lookup"><span data-stu-id="77eea-117">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77eea-118">子元素</span><span class="sxs-lookup"><span data-stu-id="77eea-118">Child Elements</span></span>  
 <span data-ttu-id="77eea-119">无。</span><span class="sxs-lookup"><span data-stu-id="77eea-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77eea-120">父元素</span><span class="sxs-lookup"><span data-stu-id="77eea-120">Parent Elements</span></span>  
  
|<span data-ttu-id="77eea-121">元素</span><span class="sxs-lookup"><span data-stu-id="77eea-121">Element</span></span>|<span data-ttu-id="77eea-122">描述</span><span class="sxs-lookup"><span data-stu-id="77eea-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77eea-123">\<筛选器 ></span><span class="sxs-lookup"><span data-stu-id="77eea-123">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters.md)|<span data-ttu-id="77eea-124">包含用于控制所记录的消息类型的 XPath 筛选器集合。</span><span class="sxs-lookup"><span data-stu-id="77eea-124">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77eea-125">备注</span><span class="sxs-lookup"><span data-stu-id="77eea-125">Remarks</span></span>  
 <span data-ttu-id="77eea-126">如果将 `logMessagesAtTransportLevel` 指定为 `true`，筛选器将只应用于传输层。</span><span class="sxs-lookup"><span data-stu-id="77eea-126">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="77eea-127">筛选器不影响服务级别和格式不正确的消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="77eea-127">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="77eea-128">若要向集合添加筛选器，请使用 `add` 关键字。</span><span class="sxs-lookup"><span data-stu-id="77eea-128">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="77eea-129">如果定义一个或多个筛选器，则仅记录与其中至少一个筛选器相匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="77eea-129">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="77eea-130">如果未定义任何筛选器，则所有消息都可通过。</span><span class="sxs-lookup"><span data-stu-id="77eea-130">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="77eea-131">筛选器支持完整的 XPath 语法，并按照其在配置文件中出现的顺序进行应用。</span><span class="sxs-lookup"><span data-stu-id="77eea-131">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="77eea-132">存在语法错误的筛选器会导致配置异常。</span><span class="sxs-lookup"><span data-stu-id="77eea-132">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="77eea-133">下面的示例演示如何配置一个筛选器，它仅记录具有 SOAP 标头部分的消息。</span><span class="sxs-lookup"><span data-stu-id="77eea-133">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77eea-134">示例</span><span class="sxs-lookup"><span data-stu-id="77eea-134">Example</span></span>  
 <span data-ttu-id="77eea-135">下面的示例演示如何配置一个筛选器，它仅记录具有 SOAP 标头部分的消息。</span><span class="sxs-lookup"><span data-stu-id="77eea-135">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"  
     logMalformedMessages="true" logMessagesAtServiceLevel="true"  
     logMessagesAtTransportLevel="true" maxMessagesToLog="420">  
     <filters>  
        <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">  
                        /soap:Envelope/soap:Headers  
        </add>  
     </filters>  
</messageLogging>  
```  
  
## <a name="see-also"></a><span data-ttu-id="77eea-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="77eea-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement>  
 <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>  
 <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>  
 [<span data-ttu-id="77eea-137">配置消息日志记录</span><span class="sxs-lookup"><span data-stu-id="77eea-137">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [<span data-ttu-id="77eea-138">配置消息日志记录</span><span class="sxs-lookup"><span data-stu-id="77eea-138">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
 [<span data-ttu-id="77eea-139">\<messageLogging ></span><span class="sxs-lookup"><span data-stu-id="77eea-139">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
