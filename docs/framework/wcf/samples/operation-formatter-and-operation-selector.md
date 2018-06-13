---
title: 操作格式化程序和操作选择器
ms.date: 03/30/2017
ms.assetid: 1c27e9fe-11f8-4377-8140-828207b98a0e
ms.openlocfilehash: db548e99c99ba6f29cc1c6e998d0e7485cd41046
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33808655"
---
# <a name="operation-formatter-and-operation-selector"></a><span data-ttu-id="1ae0f-102">操作格式化程序和操作选择器</span><span class="sxs-lookup"><span data-stu-id="1ae0f-102">Operation Formatter and Operation Selector</span></span>
<span data-ttu-id="1ae0f-103">此示例演示如何使用 Windows Communication Foundation (WCF) 扩展点以允许从 WCF 需要以不同格式的消息数据。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-103">This sample demonstrates how Windows Communication Foundation (WCF) extensibility points can be used to allow message data in a different format from what WCF expects.</span></span> <span data-ttu-id="1ae0f-104">默认情况下，WCF 格式化程序预期方法参数要包括在`soap:body`元素。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-104">By default, WCF formatters expect method parameters to be included under the `soap:body` element.</span></span> <span data-ttu-id="1ae0f-105">但是，此示例演示如何实现一个自定义操作格式化程序，用于分析 HTTP GET 查询字符串中的参数数据并使用该数据调用方法。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-105">The sample shows how to implement a custom operation formatter that parses parameter data from an HTTP GET query string instead and invokes methods using that data.</span></span>  
  
 <span data-ttu-id="1ae0f-106">示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，该类实现`ICalculator`服务协定。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-106">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="1ae0f-107">它演示如何更改 Add、Subtract、Multiply 和 Divide 消息，以便对客户端到服务器请求使用 HTTP GET，对服务器到客户端响应使用带有 POX 消息的 HTTP POST。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-107">It shows how Add, Subtract, Multiply, and Divide messages can be changed to use HTTP GET for client-to-server requests and HTTP POST with POX messages for server-to-client responses.</span></span>  
  
 <span data-ttu-id="1ae0f-108">为此，此示例提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="1ae0f-108">To do so, the sample provides the following:</span></span>  
  
-   <span data-ttu-id="1ae0f-109">`QueryStringFormatter`，它分别为客户端和服务器实现 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> 和 <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>，并处理查询字符串中的数据。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-109">`QueryStringFormatter`, which implements <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> for the client and server, respectively, and processes the data in the query string.</span></span>  
  
-   <span data-ttu-id="1ae0f-110">`UriOperationSelector`，它在服务器上实现 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>，以便基于 GET 请求中的操作名称执行操作调度。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-110">`UriOperationSelector`, which implements <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> on the server to perform operation dispatch based on the operation name in the GET request.</span></span>  
  
-   <span data-ttu-id="1ae0f-111">`EnableHttpGetRequestsBehavior` 终结点行为（和对应的配置），它向运行库中添加必要的操作选择器。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-111">`EnableHttpGetRequestsBehavior` endpoint behavior (and corresponding configuration), which adds the necessary operation selector to the runtime.</span></span>  
  
-   <span data-ttu-id="1ae0f-112">演示如何在运行库中插入新的操作格式化程序。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-112">Shows how to insert a new operation formatter into the runtime.</span></span>  
  
-   <span data-ttu-id="1ae0f-113">在此示例中，客户端和服务都是控制台应用程序 (.exe)。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-113">In this sample, both the client and the service are console applications (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ae0f-114">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="key-concepts"></a><span data-ttu-id="1ae0f-115">主要概念</span><span class="sxs-lookup"><span data-stu-id="1ae0f-115">Key Concepts</span></span>  
 <span data-ttu-id="1ae0f-116">`QueryStringFormatter` -操作格式化程序是负责将消息转换为的参数对象数组和数组中的一条消息到参数对象的 WCF 中的组件。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-116">`QueryStringFormatter` - The operation formatter is the component in WCF that is responsible for converting a message into an array of parameter objects and an array of parameter objects into a message.</span></span> <span data-ttu-id="1ae0f-117">这在客户端是使用 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> 接口完成的，在服务器上是使用 <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> 接口完成的。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-117">This is done on the client using the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> interface and on the server with the <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface.</span></span> <span data-ttu-id="1ae0f-118">通过这些接口，用户可以从 `Serialize` 和 `Deserialize` 方法获得请求和响应消息。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-118">These interfaces enable users to get the request and response messages from the `Serialize` and `Deserialize` methods.</span></span>  
  
 <span data-ttu-id="1ae0f-119">在此示例中，`QueryStringFormatter` 同时实现了这两个接口，并且在客户端和服务器上均已实现。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-119">In this sample, `QueryStringFormatter` implements both of these interfaces and is implemented on the client and server.</span></span>  
  
 <span data-ttu-id="1ae0f-120">请求：</span><span class="sxs-lookup"><span data-stu-id="1ae0f-120">Request:</span></span>  
  
-   <span data-ttu-id="1ae0f-121">此示例使用 <xref:System.ComponentModel.TypeConverter> 类将请求消息中的参数数据转换为字符串，并将字符串转换为参数数据。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-121">The sample uses the <xref:System.ComponentModel.TypeConverter> class to convert parameter data in the request message to and from strings.</span></span> <span data-ttu-id="1ae0f-122">如果 <xref:System.ComponentModel.TypeConverter> 对某个特定的类型不可用，示例格式化程序将引发异常。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-122">If a <xref:System.ComponentModel.TypeConverter> is not available for a specific type, the sample formatter throws an exception.</span></span>  
  
-   <span data-ttu-id="1ae0f-123">在客户端上的 `IClientMessageFormatter.SerializeRequest` 方法中，格式化程序创建具有相应“收件人”地址的 URI，并将操作名称作为后缀附加在后面。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-123">In the `IClientMessageFormatter.SerializeRequest` method on the client, the formatter creates a URI with the appropriate To address and appends the operation name as a suffix.</span></span> <span data-ttu-id="1ae0f-124">此名称用于调度给服务器上的相应操作。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-124">This name is used to dispatch to the appropriate operation on the server.</span></span> <span data-ttu-id="1ae0f-125">然后它采用参数对象数组，并使用 <xref:System.ComponentModel.TypeConverter> 类转换的参数名称和值将参数数据序列化为 URI 查询字符串。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-125">It then takes the array of parameter objects and serializes the parameter data to the URI query string using parameter names and the values converted by the <xref:System.ComponentModel.TypeConverter> class.</span></span> <span data-ttu-id="1ae0f-126">接着，<xref:System.ServiceModel.Channels.MessageHeaders.To%2A> 和 <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> 属性设置为该 URI。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-126">The <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> and <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> properties are then set to this URI.</span></span> <span data-ttu-id="1ae0f-127">通过 <xref:System.ServiceModel.Channels.MessageProperties> 属性访问 <xref:System.ServiceModel.Channels.Message.Properties%2A>。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-127"><xref:System.ServiceModel.Channels.MessageProperties> is accessed through the <xref:System.ServiceModel.Channels.Message.Properties%2A> property.</span></span>  
  
-   <span data-ttu-id="1ae0f-128">在服务器上的 `IDispatchMessageFormatter.DeserializeRequest` 方法中，格式化程序在传入请求消息属性中检索 `Via` URI。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-128">In the `IDispatchMessageFormatter.DeserializeRequest` method on the server, the formatter retrieves the `Via` URI in the incoming request message properties.</span></span> <span data-ttu-id="1ae0f-129">它将 URI 查询字符串中的名称-值对分析为参数名称和值，并使用参数名称和值填充传递给该方法的参数数组。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-129">It parses the name-value pairs in the URI query string into parameter names and values and uses the parameter names and values to populate the array of parameters passed into the method.</span></span> <span data-ttu-id="1ae0f-130">请注意，因为操作调度已经发生，所以此方法中忽略了操作名称后缀。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-130">Note that operation dispatch has already occurred, so the operation name suffix is ignored in this method.</span></span>  
  
 <span data-ttu-id="1ae0f-131">响应：</span><span class="sxs-lookup"><span data-stu-id="1ae0f-131">Response:</span></span>  
  
-   <span data-ttu-id="1ae0f-132">在此示例中，HTTP GET 只用于请求。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-132">In this sample, HTTP GET is used only for the request.</span></span> <span data-ttu-id="1ae0f-133">该格式化程序将响应的发送委托给本来用于生成 XML 消息的原始格式化程序。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-133">The formatter delegates the sending of the response to the original formatter that would have been used to generate an XML message.</span></span> <span data-ttu-id="1ae0f-134">此示例的目的之一是演示如何实现此类委托格式化程序。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-134">One of the goals of this sample is to show how such a delegating formatter can be implemented.</span></span>  
  
### <a name="uripathsuffixoperationselector-class"></a><span data-ttu-id="1ae0f-135">UriPathSuffixOperationSelector 类</span><span class="sxs-lookup"><span data-stu-id="1ae0f-135">UriPathSuffixOperationSelector Class</span></span>  
 <span data-ttu-id="1ae0f-136">用户可以通过 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> 接口实现自己的逻辑，决定应为哪个操作调度特定的消息。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-136">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface enables users to implement their own logic for which operation a particular message should be dispatched.</span></span>  
  
 <span data-ttu-id="1ae0f-137">在此示例中，必须在服务器上实现 `UriPathSuffixOperationSelector` 以选择合适的操作，因为操作名称包含在 HTTP GET URI 中，而不是包含在消息的操作标头中。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-137">In this sample, `UriPathSuffixOperationSelector` must be implemented on the server to select the appropriate operation because the operation name is included in the HTTP GET URI rather than an action header in the message.</span></span> <span data-ttu-id="1ae0f-138">此示例设置为只允许不区分大小写的操作名称。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-138">The sample is set up to allow only case-insensitive operation names.</span></span>  
  
 <span data-ttu-id="1ae0f-139">`SelectOperation` 方法采用传入消息，并在其消息属性中查找 `Via` URI。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-139">The `SelectOperation` method takes the incoming message and looks up the `Via` URI in its message properties.</span></span> <span data-ttu-id="1ae0f-140">它从 URI 中提取操作名称后缀，查看内部表以获取应将该消息调度给的操作名称，并返回该操作名称。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-140">It extracts the operation name suffix from the URI, looks up an internal table to get the operation name that the message should be dispatched to, and returns that operation name.</span></span>  
  
### <a name="enablehttpgetrequestsbehavior-class"></a><span data-ttu-id="1ae0f-141">EnableHttpGetRequestsBehavior 类</span><span class="sxs-lookup"><span data-stu-id="1ae0f-141">EnableHttpGetRequestsBehavior Class</span></span>  
 <span data-ttu-id="1ae0f-142">`UriPathSuffixOperationSelector` 组件可以通过编程方式或者通过终结点行为进行设置。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-142">The `UriPathSuffixOperationSelector` component can be set up programmatically or through an endpoint behavior.</span></span> <span data-ttu-id="1ae0f-143">此示例实现了 `EnableHttpGetRequestsBehavior` 行为，这是在服务的应用程序配置文件中指定的。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-143">The sample implements the `EnableHttpGetRequestsBehavior` behavior, which is specified in service’s application configuration file.</span></span>  
  
 <span data-ttu-id="1ae0f-144">在服务器上：</span><span class="sxs-lookup"><span data-stu-id="1ae0f-144">On the server:</span></span>  
  
 <span data-ttu-id="1ae0f-145"><xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> 设置为 <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> 实现。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-145">The <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> is set to the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementation.</span></span>  
  
 <span data-ttu-id="1ae0f-146">默认情况下，WCF 使用精确匹配的地址筛选器。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-146">By default, WCF uses an exact-match address filter.</span></span> <span data-ttu-id="1ae0f-147">传入消息中的 URI 包含一个操作名称后缀，后跟包含参数数据的查询字符串，因此终结点行为还将地址筛选器更改为前缀匹配筛选器。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-147">The URI on the incoming message contains an operation name suffix followed by a query string that contains parameter data, so the endpoint behavior also changes the address filter to be a prefix match filter.</span></span> <span data-ttu-id="1ae0f-148">它使用 WCF<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>为此目的。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-148">It uses the WCF<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> for this purpose.</span></span>  
  
### <a name="installing-operation-formatters"></a><span data-ttu-id="1ae0f-149">安装操作格式化程序</span><span class="sxs-lookup"><span data-stu-id="1ae0f-149">Installing operation formatters</span></span>  
 <span data-ttu-id="1ae0f-150">指定格式化程序的操作行为是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-150">Operation behaviors that specify formatters are unique.</span></span> <span data-ttu-id="1ae0f-151">默认情况下始终为每个操作实现这样一个行为，以创建必要的操作格式化程序。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-151">One such behavior is always implemented by default for every operation to create the necessary operation formatter.</span></span> <span data-ttu-id="1ae0f-152">但是，这些行为看起来就像另一个操作行为；它们不能通过其他任何属性进行标识。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-152">However, these behaviors look like just another operation behavior; they are not identifiable by any other attribute.</span></span> <span data-ttu-id="1ae0f-153">若要安装替换行为，实现必须查找 WCF 类型加载程序默认情况下和安装的特定格式化程序行为替换它，或添加一个兼容的行为在默认行为之后运行。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-153">To install a replacement behavior, the implementation must look for specific formatter behaviors that are installed by the WCF type loader by default and either replace it or add a compatible behavior to run after the default behavior.</span></span>  
  
 <span data-ttu-id="1ae0f-154">这些操作格式化程序行为可以在调用 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> 之前通过编程方式进行设置，或者通过指定一个在默认行为之后执行的操作行为来进行设置。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-154">These operation formatters behaviors can be set up programmatically prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> or by specifying an operation behavior that is executed after the default one.</span></span> <span data-ttu-id="1ae0f-155">但是，通过终结点行为（并进而通过配置）并不能轻松完成设置，因为行为模式不允许用一个行为替换另一个行为，或者通过其他方式修改说明树。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-155">However, it cannot easily be set up by an endpoint behavior (and therefore by configuration) because the behavior model does not allow a behavior to replace other behaviors or otherwise modify the description tree.</span></span>  
  
 <span data-ttu-id="1ae0f-156">在客户端上：</span><span class="sxs-lookup"><span data-stu-id="1ae0f-156">On the client:</span></span>  
  
 <span data-ttu-id="1ae0f-157">必须实现 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> 实现，以使其能够将请求转换为 HTTP GET 请求，并委托原始格式化程序做出响应。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-157">The <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> implementation must be implemented so that it can convert the requests into HTTP GET requests and delegate to the original formatter for responses.</span></span> <span data-ttu-id="1ae0f-158">这是通过调用 `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` 帮助器方法实现的。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-158">This is done by calling the `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method.</span></span>  
  
 <span data-ttu-id="1ae0f-159">这必须在调用 `CreateChannel` 之前完成。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-159">This must be done before calling `CreateChannel`.</span></span>  
  
```  
void ReplaceFormatterBehavior(OperationDescription operationDescription, EndpointAddress address)  
{  
    // Remove the DataContract behavior if it is present.  
    IOperationBehavior formatterBehavior = operationDescription.Behaviors.Remove<DataContractSerializerOperationBehavior>();  
    if (formatterBehavior == null)  
    {  
        // Remove the XmlSerializer behavior if it is present.  
        formatterBehavior = operationDescription.Behaviors.Remove<XmlSerializerOperationBehavior>();  
        ...  
    }  
  
    // Remember what the innerFormatterBehavior was.  
    DelegatingFormatterBehavior delegatingFormatterBehavior = new DelegatingFormatterBehavior(address);  
    delegatingFormatterBehavior.InnerFormatterBehavior = formatterBehavior;  
   operationDescription.Behaviors.Add(delegatingFormatterBehavior);  
}  
```  
  
 <span data-ttu-id="1ae0f-160">在服务器上：</span><span class="sxs-lookup"><span data-stu-id="1ae0f-160">On the server:</span></span>  
  
-   <span data-ttu-id="1ae0f-161">必须实现 <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> 接口，以使其能够读取 HTTP GET 请求，并委托原始格式化程序编写响应。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-161">The <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface must be implemented so that it can read HTTP GET requests and delegate to the original formatter for writing responses.</span></span> <span data-ttu-id="1ae0f-162">这是通过调用与客户端相同的 `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` 帮助器方法实现的（请参见前面的代码示例）。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-162">This is done by calling the same `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method as the client (see the previous code sample).</span></span>  
  
-   <span data-ttu-id="1ae0f-163">这必须在调用 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> 之前完成。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-163">This must be done before <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="1ae0f-164">在此示例中，我们演示如何在调用 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> 之前手动修改格式化程序。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-164">In this sample, we show how the formatter is manually modified before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="1ae0f-165">实现同一目标的另一种方式是从 <xref:System.ServiceModel.ServiceHost> 派生一个类，以便在打开之前调用 `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`（有关示例，请参见承载文档和示例）。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-165">Another way to achieve the same thing is to derive a class from <xref:System.ServiceModel.ServiceHost> that makes the calls to `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` before opening (please see hosting documentation and samples for examples).</span></span>  
  
### <a name="user-experience"></a><span data-ttu-id="1ae0f-166">用户体验</span><span class="sxs-lookup"><span data-stu-id="1ae0f-166">User experience</span></span>  
 <span data-ttu-id="1ae0f-167">在服务器上：</span><span class="sxs-lookup"><span data-stu-id="1ae0f-167">On the server:</span></span>  
  
-   <span data-ttu-id="1ae0f-168">服务器 `ICalculator` 实现不需要更改。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-168">The server `ICalculator` implementation does not need to change.</span></span>  
  
-   <span data-ttu-id="1ae0f-169">服务的 App.config 必须使用自定义 POX 绑定，该绑定将 `messageVersion` 元素的 `textMessageEncoding` 属性设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-169">The App.config for the service must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
-   <span data-ttu-id="1ae0f-170">服务的 App.config 还必须指定自定义 `EnableHttpGetRequestsBehavior`（通过将其添加到行为扩展部分并使用它来实现）。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-170">The App.config for the service also must specify the custom `EnableHttpGetRequestsBehavior` by adding it to the behavior extensions section and using it.</span></span>  
  
    ```xml  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="enableHttpGetRequestsBehavior">  
          <enableHttpGetRequests />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
    <extensions>  
      <behaviorExtensions>  
        <!-- Enabling HTTP GET requests: Behavior Extension -->  
        <add   
          name="enableHttpGetRequests"           type="Microsoft.ServiceModel.Samples.EnableHttpGetRequestsBehaviorElement, QueryStringFormatter, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
    ```  
  
-   <span data-ttu-id="1ae0f-171">在调用 <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> 之前添加操作格式化程序。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-171">Add operation formatters before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
 <span data-ttu-id="1ae0f-172">在客户端上：</span><span class="sxs-lookup"><span data-stu-id="1ae0f-172">On the client:</span></span>  
  
-   <span data-ttu-id="1ae0f-173">客户端实现不需要更改。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-173">The client implementation does not need to change.</span></span>  
  
-   <span data-ttu-id="1ae0f-174">客户端 App.config 必须使用自定义 POX 绑定，该绑定将 `messageVersion` 元素的 `textMessageEncoding` 属性设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-174">The App.config for the client must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span> <span data-ttu-id="1ae0f-175">与服务的一个区别在于，客户端必须允许手动寻址，以便修改传出“收件人”地址。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-175">One difference from the service is that the client must enable manual addressing so that the outgoing To address can be modified.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport manualAddressing="True" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
-   <span data-ttu-id="1ae0f-176">客户端 App.config 必须指定与服务器相同的自定义 `EnableHttpGetRequestsBehavior`。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-176">The App.config for the client must specify the same custom `EnableHttpGetRequestsBehavior` as the server.</span></span>  
  
-   <span data-ttu-id="1ae0f-177">在调用 <xref:System.ServiceModel.ChannelFactory%601.CreateChannel> 之前添加操作格式化程序。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-177">Add operation formatters before calling <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span></span>  
  
 <span data-ttu-id="1ae0f-178">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-178">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="1ae0f-179">所有四个操作（Add、Subtract、Multiply 和 Divide）都必须成功。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-179">All four operations (Add, Subtract, Multiply, and Divide) must succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1ae0f-180">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-180">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1ae0f-181">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="1ae0f-181">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1ae0f-182">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-182">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1ae0f-183">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="1ae0f-183">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Formatters\QuieryStringFormatter`  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1ae0f-184">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="1ae0f-184">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1ae0f-185">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="1ae0f-186">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="1ae0f-187">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="1ae0f-187">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae0f-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ae0f-188">See Also</span></span>
