---
title: <add> 的 <filters>
ms.date: 03/30/2017
ms.assetid: e3bf437c-dd99-49f3-9792-9a8721e6eaad
ms.openlocfilehash: 280c516b17a133930bc4b6621a8c9bc7f4781085
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850563"
---
# <a name="add-of-filters"></a><span data-ttu-id="d5eca-102">\<添加\<筛选器 > ></span><span class="sxs-lookup"><span data-stu-id="d5eca-102">\<add> of \<filters></span></span>
<span data-ttu-id="d5eca-103">一个 XPath 筛选器，用于指定要记录的消息的种类。</span><span class="sxs-lookup"><span data-stu-id="d5eca-103">A XPath filter that specifies the kind of message to be logged.</span></span>  
  
<span data-ttu-id="d5eca-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d5eca-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d5eca-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d5eca-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d5eca-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<诊断 >** ](diagnostics.md)</span><span class="sxs-lookup"><span data-stu-id="d5eca-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)</span></span>\
<span data-ttu-id="d5eca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<messageLogging >** ](messagelogging.md)</span><span class="sxs-lookup"><span data-stu-id="d5eca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<messageLogging>**](messagelogging.md)</span></span>\
<span data-ttu-id="d5eca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<筛选器 >** ](filters.md)</span><span class="sxs-lookup"><span data-stu-id="d5eca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters.md)</span></span>\
<span data-ttu-id="d5eca-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="d5eca-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5eca-110">语法</span><span class="sxs-lookup"><span data-stu-id="d5eca-110">Syntax</span></span>  
  
```xml  
<filters>
  <add filter="String" />
</filters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5eca-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d5eca-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d5eca-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d5eca-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5eca-113">特性</span><span class="sxs-lookup"><span data-stu-id="d5eca-113">Attributes</span></span>  
  
|<span data-ttu-id="d5eca-114">特性</span><span class="sxs-lookup"><span data-stu-id="d5eca-114">Attribute</span></span>|<span data-ttu-id="d5eca-115">描述</span><span class="sxs-lookup"><span data-stu-id="d5eca-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5eca-116">筛选器</span><span class="sxs-lookup"><span data-stu-id="d5eca-116">filter</span></span>|<span data-ttu-id="d5eca-117">一个字符串，用于指定由 XPath 1.0 表达式定义的 XML 文档的查询。</span><span class="sxs-lookup"><span data-stu-id="d5eca-117">A string that specifies a query on an XML document defined by an XPath 1.0 expression.</span></span> <span data-ttu-id="d5eca-118">有关详细信息，请参阅 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> 。</span><span class="sxs-lookup"><span data-stu-id="d5eca-118">For more information, see <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5eca-119">子元素</span><span class="sxs-lookup"><span data-stu-id="d5eca-119">Child Elements</span></span>  
 <span data-ttu-id="d5eca-120">无。</span><span class="sxs-lookup"><span data-stu-id="d5eca-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5eca-121">父元素</span><span class="sxs-lookup"><span data-stu-id="d5eca-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d5eca-122">元素</span><span class="sxs-lookup"><span data-stu-id="d5eca-122">Element</span></span>|<span data-ttu-id="d5eca-123">描述</span><span class="sxs-lookup"><span data-stu-id="d5eca-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5eca-124">\<filters></span><span class="sxs-lookup"><span data-stu-id="d5eca-124">\<filters></span></span>](filters.md)|<span data-ttu-id="d5eca-125">包含用于控制所记录的消息类型的 XPath 筛选器集合。</span><span class="sxs-lookup"><span data-stu-id="d5eca-125">Contains a collection of XPath filters used to control what kind of message is logged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5eca-126">备注</span><span class="sxs-lookup"><span data-stu-id="d5eca-126">Remarks</span></span>  
 <span data-ttu-id="d5eca-127">如果将 `logMessagesAtTransportLevel` 指定为 `true`，筛选器将只应用于传输层。</span><span class="sxs-lookup"><span data-stu-id="d5eca-127">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="d5eca-128">筛选器不影响服务级别和格式不正确的消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="d5eca-128">Service level and malformed message logging are not affected by filters.</span></span>  
  
 <span data-ttu-id="d5eca-129">若要向集合添加筛选器，请使用 `add` 关键字。</span><span class="sxs-lookup"><span data-stu-id="d5eca-129">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="d5eca-130">如果定义一个或多个筛选器，则仅记录与其中至少一个筛选器相匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="d5eca-130">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="d5eca-131">如果未定义任何筛选器，则所有消息都可通过。</span><span class="sxs-lookup"><span data-stu-id="d5eca-131">If no filter is defined, all messages pass through.</span></span>  
  
 <span data-ttu-id="d5eca-132">筛选器支持完整的 XPath 语法，并按照其在配置文件中出现的顺序进行应用。</span><span class="sxs-lookup"><span data-stu-id="d5eca-132">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="d5eca-133">存在语法错误的筛选器会导致配置异常。</span><span class="sxs-lookup"><span data-stu-id="d5eca-133">A syntactically incorrect filter results in a configuration exception.</span></span>  
  
 <span data-ttu-id="d5eca-134">下面的示例演示如何配置一个筛选器，它仅记录具有 SOAP 标头部分的消息。</span><span class="sxs-lookup"><span data-stu-id="d5eca-134">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5eca-135">示例</span><span class="sxs-lookup"><span data-stu-id="d5eca-135">Example</span></span>  
 <span data-ttu-id="d5eca-136">下面的示例演示如何配置一个筛选器，它仅记录具有 SOAP 标头部分的消息。</span><span class="sxs-lookup"><span data-stu-id="d5eca-136">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>  
  
```xml  
<messageLogging logEntireMessage="true"
                logMalformedMessages="true"
                logMessagesAtServiceLevel="true"
                logMessagesAtTransportLevel="true"
                maxMessagesToLog="420">
  <filters>
    <add xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
      /soap:Envelope/soap:Headers
    </add>
  </filters>
</messageLogging>
```  
  
## <a name="see-also"></a><span data-ttu-id="d5eca-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5eca-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="d5eca-138">配置消息日志记录</span><span class="sxs-lookup"><span data-stu-id="d5eca-138">Configuring Message Logging</span></span>](../../../wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="d5eca-139">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="d5eca-139">\<messageLogging></span></span>](messagelogging.md)
