---
title: '&lt;filters&gt;'
ms.date: 03/30/2017
ms.assetid: 37a87222-ec78-4728-8105-9ca1bd961f0c
ms.openlocfilehash: 5f50b1ad4abfa77022a17d6497b614721382ec1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600188"
---
# <a name="ltfiltersgt"></a><span data-ttu-id="1b24e-102">&lt;filters&gt;</span><span class="sxs-lookup"><span data-stu-id="1b24e-102">&lt;filters&gt;</span></span>

<span data-ttu-id="1b24e-103">`filters` 元素包含用于控制所记录的消息类型的 XPath 筛选器集合。</span><span class="sxs-lookup"><span data-stu-id="1b24e-103">The `filters` element holds a collection of XPath filters used to control what kind of message is logged.</span></span>

<span data-ttu-id="1b24e-104">如果将 `logMessagesAtTransportLevel` 指定为 `true`，筛选器将只应用于传输层。</span><span class="sxs-lookup"><span data-stu-id="1b24e-104">Filters are applied only at the transport layer, specified by `logMessagesAtTransportLevel` is `true`.</span></span> <span data-ttu-id="1b24e-105">筛选器不影响服务级别和格式不正确的消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="1b24e-105">Service level and malformed message logging are not affected by filters.</span></span>

<span data-ttu-id="1b24e-106">若要向集合添加筛选器，请使用 `add` 关键字。</span><span class="sxs-lookup"><span data-stu-id="1b24e-106">To add a filter to the collection, use the `add` keyword.</span></span> <span data-ttu-id="1b24e-107">如果定义一个或多个筛选器，则仅记录与其中至少一个筛选器相匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="1b24e-107">When one or more filters are defined, only messages that match at least one of the filters are logged.</span></span> <span data-ttu-id="1b24e-108">如果未定义任何筛选器，则所有消息都可通过。</span><span class="sxs-lookup"><span data-stu-id="1b24e-108">If no filter is defined, all messages pass through.</span></span>

<span data-ttu-id="1b24e-109">筛选器支持完整的 XPath 语法，并按照其在配置文件中出现的顺序进行应用。</span><span class="sxs-lookup"><span data-stu-id="1b24e-109">Filters support the full XPath syntax, and are applied in the order they appear in the configuration file.</span></span> <span data-ttu-id="1b24e-110">存在语法错误的筛选器会导致配置异常。</span><span class="sxs-lookup"><span data-stu-id="1b24e-110">A syntactically incorrect filter results in a configuration exception.</span></span>

<span data-ttu-id="1b24e-111">下面的示例演示如何配置一个筛选器，它仅记录具有 SOAP 标头部分的消息。</span><span class="sxs-lookup"><span data-stu-id="1b24e-111">The following is an example of how to configure a filter that records only messages that have a SOAP Header section.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="1b24e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b24e-112">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement>
- <xref:System.ServiceModel.Configuration.MessageLoggingElement.Filters%2A>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElementCollection>
- <xref:System.ServiceModel.Configuration.XPathMessageFilterElement>
- <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>
- [<span data-ttu-id="1b24e-113">配置消息日志记录</span><span class="sxs-lookup"><span data-stu-id="1b24e-113">Configuring Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)
- [<span data-ttu-id="1b24e-114">\<messageLogging></span><span class="sxs-lookup"><span data-stu-id="1b24e-114">\<messageLogging></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)
