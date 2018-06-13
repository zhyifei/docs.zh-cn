---
title: 处理异常和错误
ms.date: 03/30/2017
ms.assetid: a64d01c6-f221-4f58-93e5-da4e87a5682e
ms.openlocfilehash: 494a0665f5bad2c7da3998cf77ced79314ca2f36
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809555"
---
# <a name="handling-exceptions-and-faults"></a><span data-ttu-id="4d291-102">处理异常和错误</span><span class="sxs-lookup"><span data-stu-id="4d291-102">Handling Exceptions and Faults</span></span>
<span data-ttu-id="4d291-103">异常用来在服务或客户端实现中在本地传达错误，</span><span class="sxs-lookup"><span data-stu-id="4d291-103">Exceptions are used to communicate errors locally within the service or the client implementation.</span></span> <span data-ttu-id="4d291-104">而错误则用来跨服务边界传达错误，如在服务器与客户端之间传达。</span><span class="sxs-lookup"><span data-stu-id="4d291-104">Faults, on the other hand, are used to communicate errors across service boundaries, such as from the server to the client or vice versa.</span></span> <span data-ttu-id="4d291-105">除了错误以外，传输通道也常常使用传输特定的机制来传达传输级错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-105">In addition to faults, transport channels often use transport-specific mechanisms to communicate transport-level errors.</span></span> <span data-ttu-id="4d291-106">例如，HTTP 传输机制使用状态码（如 404）来传达不存在的终结点 URL（不存在发回错误的终结点）。</span><span class="sxs-lookup"><span data-stu-id="4d291-106">For example, HTTP transport uses status codes such as 404 to communicate a non-existing endpoint URL (there is no endpoint to send back a fault).</span></span> <span data-ttu-id="4d291-107">本文档由三部分组成，它们为自定义通道的作者提供指南。</span><span class="sxs-lookup"><span data-stu-id="4d291-107">This document consists of three sections that provide guidance to custom channel authors.</span></span> <span data-ttu-id="4d291-108">第一部分提供关于何时以及如何定义和引发异常的指南。</span><span class="sxs-lookup"><span data-stu-id="4d291-108">The first section provides guidance on when and how to define and throw exceptions.</span></span> <span data-ttu-id="4d291-109">第二部分提供关于生成和使用错误的指南。</span><span class="sxs-lookup"><span data-stu-id="4d291-109">The second section provides guidance around generating and consuming faults.</span></span> <span data-ttu-id="4d291-110">第三部分说明如何提供跟踪信息来帮助自定义通道用户对所运行的应用程序进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="4d291-110">The third section explains how to provide trace information to aid the user of your custom channel in troubleshooting running applications.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="4d291-111">异常</span><span class="sxs-lookup"><span data-stu-id="4d291-111">Exceptions</span></span>  
 <span data-ttu-id="4d291-112">在引发异常时需要牢记两件事情：第一，异常的类型必须允许用户编写能对异常做出适当反应的正确代码。</span><span class="sxs-lookup"><span data-stu-id="4d291-112">There are two things to keep in mind when throwing an exception: First it has to be of a type that allows users to write correct code that can react appropriately to the exception.</span></span> <span data-ttu-id="4d291-113">第二，异常必须为用户提供足够的信息，使用户能了解究竟哪里出现了故障，该故障带来的影响以及如何修复该故障。</span><span class="sxs-lookup"><span data-stu-id="4d291-113">Second, it has to provide enough information for the user to understand what went wrong, the failure impact, and how to fix it.</span></span> <span data-ttu-id="4d291-114">以下部分提供关于异常的类型和消息的 Windows Communication Foundation (WCF) 通道指南。</span><span class="sxs-lookup"><span data-stu-id="4d291-114">The following sections give guidance around exception types and messages for Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="4d291-115">“异常的设计准则”文档中也有关于 .NET 中的异常的一般性指南。</span><span class="sxs-lookup"><span data-stu-id="4d291-115">There is also general guidance around exceptions in .NET in the Design Guidelines for Exceptions document.</span></span>  
  
### <a name="exception-types"></a><span data-ttu-id="4d291-116">异常类型</span><span class="sxs-lookup"><span data-stu-id="4d291-116">Exception Types</span></span>  
 <span data-ttu-id="4d291-117">由通道引发的所有异常都必须是 <xref:System.TimeoutException?displayProperty=nameWithType>、<xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> 或者是派生自 <xref:System.ServiceModel.CommunicationException> 的类型</span><span class="sxs-lookup"><span data-stu-id="4d291-117">All exceptions thrown by channels must be either a <xref:System.TimeoutException?displayProperty=nameWithType>, <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>, or a type derived from <xref:System.ServiceModel.CommunicationException>.</span></span> <span data-ttu-id="4d291-118">（还可能会引发诸如 <xref:System.ObjectDisposedException> 之类的异常，但这仅仅是为了指示调用代码误用了通道。</span><span class="sxs-lookup"><span data-stu-id="4d291-118">(Exceptions such as <xref:System.ObjectDisposedException> may also be thrown, but only to indicate that the calling code has misused the channel.</span></span> <span data-ttu-id="4d291-119">如果某个通道的使用正确无误，则它只能引发给定的异常）。WCF 提供了七个派生自的异常类型<xref:System.ServiceModel.CommunicationException>，它们设计为供通道。</span><span class="sxs-lookup"><span data-stu-id="4d291-119">If a channel is used correctly, it must only throw the given exceptions.) WCF provides seven exception types that derive from <xref:System.ServiceModel.CommunicationException> and are designed to be used by channels.</span></span> <span data-ttu-id="4d291-120">还存在其他从 <xref:System.ServiceModel.CommunicationException> 派生的异常，这些异常设计用于系统的其他部分。</span><span class="sxs-lookup"><span data-stu-id="4d291-120">There are other <xref:System.ServiceModel.CommunicationException>-derived exceptions that are designed to be used by other parts of the system.</span></span> <span data-ttu-id="4d291-121">这些异常类型包括：</span><span class="sxs-lookup"><span data-stu-id="4d291-121">These exception types are:</span></span>  
  
|<span data-ttu-id="4d291-122">异常类型</span><span class="sxs-lookup"><span data-stu-id="4d291-122">Exception Type</span></span>|<span data-ttu-id="4d291-123">含义</span><span class="sxs-lookup"><span data-stu-id="4d291-123">Meaning</span></span>|<span data-ttu-id="4d291-124">内部异常的内容</span><span class="sxs-lookup"><span data-stu-id="4d291-124">Inner Exception Content</span></span>|<span data-ttu-id="4d291-125">恢复策略</span><span class="sxs-lookup"><span data-stu-id="4d291-125">Recovery Strategy</span></span>|  
|--------------------|-------------|-----------------------------|-----------------------|  
|<xref:System.ServiceModel.AddressAlreadyInUseException>|<span data-ttu-id="4d291-126">为进行侦听而指定的终结点地址已在使用。</span><span class="sxs-lookup"><span data-stu-id="4d291-126">The endpoint address specified for listening is already in use.</span></span>|<span data-ttu-id="4d291-127">如果存在，则提供有关引起此异常的传输错误的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-127">If present, provides more details about the transport error that caused this exception.</span></span> <span data-ttu-id="4d291-128">例如，</span><span class="sxs-lookup"><span data-stu-id="4d291-128">For example.</span></span> <span data-ttu-id="4d291-129"><xref:System.IO.PipeException>, <xref:System.Net.HttpListenerException> 或 <xref:System.Net.Sockets.SocketException>。</span><span class="sxs-lookup"><span data-stu-id="4d291-129"><xref:System.IO.PipeException>, <xref:System.Net.HttpListenerException>, or <xref:System.Net.Sockets.SocketException>.</span></span>|<span data-ttu-id="4d291-130">请尝试使用其他地址。</span><span class="sxs-lookup"><span data-stu-id="4d291-130">Try a different address.</span></span>|  
|<xref:System.ServiceModel.AddressAccessDeniedException>|<span data-ttu-id="4d291-131">不允许该进程访问为进行侦听而指定的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="4d291-131">The process is not allowed access to the endpoint address specified for listening.</span></span>|<span data-ttu-id="4d291-132">如果存在，则提供有关引起此异常的传输错误的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-132">If present, provides more details about the transport error that caused this exception.</span></span> <span data-ttu-id="4d291-133">例如，<xref:System.IO.PipeException> 或 <xref:System.Net.HttpListenerException>。</span><span class="sxs-lookup"><span data-stu-id="4d291-133">For example, <xref:System.IO.PipeException>, or <xref:System.Net.HttpListenerException>.</span></span>|<span data-ttu-id="4d291-134">请尝试使用其他凭据。</span><span class="sxs-lookup"><span data-stu-id="4d291-134">Try with different credentials.</span></span>|  
|<xref:System.ServiceModel.CommunicationObjectFaultedException>|<span data-ttu-id="4d291-135"><xref:System.ServiceModel.ICommunicationObject>正在使用处于出错状态 (有关详细信息，请参阅[了解状态更改](../../../../docs/framework/wcf/extending/understanding-state-changes.md))。</span><span class="sxs-lookup"><span data-stu-id="4d291-135">The <xref:System.ServiceModel.ICommunicationObject> being used is in the Faulted state (for more information, see [Understanding State Changes](../../../../docs/framework/wcf/extending/understanding-state-changes.md)).</span></span> <span data-ttu-id="4d291-136">请注意，当具有多个挂起调用的对象转变为“出错”状态时，只有一个调用引发与该故障有关的异常，而其余调用都引发 <xref:System.ServiceModel.CommunicationObjectFaultedException>。</span><span class="sxs-lookup"><span data-stu-id="4d291-136">Note that when an object with multiple pending calls transitions to the Faulted state, only one call throws an exception that is related to the failure and the rest of the calls throw a <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span></span> <span data-ttu-id="4d291-137">引发此异常的原因通常在于，应用程序忽略了某个异常并尝试使用已出错的对象，而在其中使用该对象的线程可能不是捕获原始异常的线程。</span><span class="sxs-lookup"><span data-stu-id="4d291-137">This exception is typically thrown because an application overlooks some exception and tries to use an already faulted object, possibly on a thread other than the one that caught the original exception.</span></span>|<span data-ttu-id="4d291-138">如果存在，则提供有关内部异常的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-138">If present provides details about the inner exception.</span></span>|<span data-ttu-id="4d291-139">新建一个对象。</span><span class="sxs-lookup"><span data-stu-id="4d291-139">Create a new object.</span></span> <span data-ttu-id="4d291-140">请注意，根据首先导致 <xref:System.ServiceModel.ICommunicationObject> 出错的原因，可能还需要完成其他工作来进行恢复。</span><span class="sxs-lookup"><span data-stu-id="4d291-140">Note that depending on what caused the <xref:System.ServiceModel.ICommunicationObject> to fault in the first place, there may be other work required to recover.</span></span>|  
|<xref:System.ServiceModel.CommunicationObjectAbortedException>|<span data-ttu-id="4d291-141"><xref:System.ServiceModel.ICommunicationObject>正在使用已中止 (有关详细信息，请参阅[了解状态更改](../../../../docs/framework/wcf/extending/understanding-state-changes.md))。</span><span class="sxs-lookup"><span data-stu-id="4d291-141">The <xref:System.ServiceModel.ICommunicationObject> being used has been Aborted (for more information, see [Understanding State Changes](../../../../docs/framework/wcf/extending/understanding-state-changes.md)).</span></span> <span data-ttu-id="4d291-142">与 <xref:System.ServiceModel.CommunicationObjectFaultedException> 相似，此异常指示应用程序已在该对象上调用了 <xref:System.ServiceModel.ICommunicationObject.Abort%2A>（有可能是从另一个线程调用的），而且该对象会因此而不再可用。</span><span class="sxs-lookup"><span data-stu-id="4d291-142">Similar to <xref:System.ServiceModel.CommunicationObjectFaultedException>, his exception indicates the application has called <xref:System.ServiceModel.ICommunicationObject.Abort%2A> on the object, possibly from another thread, and the object is no longer usable for that reason.</span></span>|<span data-ttu-id="4d291-143">如果存在，则提供有关内部异常的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-143">If present provides details about the inner exception.</span></span>|<span data-ttu-id="4d291-144">新建一个对象。</span><span class="sxs-lookup"><span data-stu-id="4d291-144">Create a new object.</span></span> <span data-ttu-id="4d291-145">请注意，根据首先导致 <xref:System.ServiceModel.ICommunicationObject> 中止的原因，可能还需要完成其他工作来进行恢复。</span><span class="sxs-lookup"><span data-stu-id="4d291-145">Note that depending on what caused the <xref:System.ServiceModel.ICommunicationObject> to abort in the first place, there may be other work required to recover.</span></span>|  
|<xref:System.ServiceModel.EndpointNotFoundException>|<span data-ttu-id="4d291-146">目标远程终结点未在进行侦听。</span><span class="sxs-lookup"><span data-stu-id="4d291-146">The target remote endpoint is not listening.</span></span> <span data-ttu-id="4d291-147">这可能是由于终结点地址的任何部分不正确、无法解析或者终结点已关闭。</span><span class="sxs-lookup"><span data-stu-id="4d291-147">This can result from any part of the endpoint address being incorrect, irresolvable, or the endpoint being down.</span></span> <span data-ttu-id="4d291-148">这方面的例子有 DNS 错误、队列管理器不可用以及服务未在运行。</span><span class="sxs-lookup"><span data-stu-id="4d291-148">Examples include DNS error, Queue Manager not available, and service not running.</span></span>|<span data-ttu-id="4d291-149">内部异常提供通常来自基础传输的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-149">The inner exception provides details, typically from the underlying transport.</span></span>|<span data-ttu-id="4d291-150">请尝试使用其他地址。</span><span class="sxs-lookup"><span data-stu-id="4d291-150">Try a different address.</span></span> <span data-ttu-id="4d291-151">或者，对于服务已关闭的情况，发送方可以稍等片刻再重试。</span><span class="sxs-lookup"><span data-stu-id="4d291-151">Alternatively, the sender may wait a while and try again in case the service was down</span></span>|  
|<xref:System.ServiceModel.ProtocolException>|<span data-ttu-id="4d291-152">终结点策略中所描述的通信协议在终结点之间不符。</span><span class="sxs-lookup"><span data-stu-id="4d291-152">The communication protocols, as described by the endpoint’s policy, are mismatched between endpoints.</span></span> <span data-ttu-id="4d291-153">例如，组帧内容类型不匹配或者超过了最大消息大小。</span><span class="sxs-lookup"><span data-stu-id="4d291-153">For example, framing content type mismatch or max message size exceeded.</span></span>|<span data-ttu-id="4d291-154">如果存在，则提供有关特定协议错误的更多信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-154">If present provides more information about the specific protocol error.</span></span> <span data-ttu-id="4d291-155">例如，如果出错原因是由于超过了 MaxReceivedMessageSize，则 <xref:System.ServiceModel.QuotaExceededException> 为内部异常。</span><span class="sxs-lookup"><span data-stu-id="4d291-155">For example, <xref:System.ServiceModel.QuotaExceededException> is the inner exception when the error cause is exceeding MaxReceivedMessageSize.</span></span>|<span data-ttu-id="4d291-156">恢复：请确保发送方的协议设置与接收方的协议设置相匹配。</span><span class="sxs-lookup"><span data-stu-id="4d291-156">Recovery: Ensure sender and received protocol settings match.</span></span> <span data-ttu-id="4d291-157">保证这一点的一种方法是，重新导入服务终结点的元数据（策略）并使用所生成的绑定来重新创建通道。</span><span class="sxs-lookup"><span data-stu-id="4d291-157">One way to do this is to re-import the service endpoint’s metadata (policy) and use the generated binding to recreate the channel.</span></span>|  
|<xref:System.ServiceModel.ServerTooBusyException>|<span data-ttu-id="4d291-158">远程终结点正在侦听，但不准备处理消息。</span><span class="sxs-lookup"><span data-stu-id="4d291-158">The remote endpoint is listening but is not prepared to process messages.</span></span>|<span data-ttu-id="4d291-159">如果存在，则该内部异常提供有关 SOAP 错误或传输级错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-159">If present, the inner Exception provides the SOAP fault or transport-level error details.</span></span>|<span data-ttu-id="4d291-160">恢复：请稍等片刻再重试该操作。</span><span class="sxs-lookup"><span data-stu-id="4d291-160">Recovery: Wait and retry the operation later.</span></span>|  
|<xref:System.TimeoutException>|<span data-ttu-id="4d291-161">该操作未能在超时期限内完成。</span><span class="sxs-lookup"><span data-stu-id="4d291-161">The operation failed to complete within the timeout period.</span></span>|<span data-ttu-id="4d291-162">可能会提供有关超时的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-162">May provide details about the timeout.</span></span>|<span data-ttu-id="4d291-163">请稍等片刻再重试该操作。</span><span class="sxs-lookup"><span data-stu-id="4d291-163">Wait and retry the operation later.</span></span>|  
  
 <span data-ttu-id="4d291-164">只有在该类型所对应的特定恢复策略不同于现有的全部异常类型时，才定义新的异常类型。</span><span class="sxs-lookup"><span data-stu-id="4d291-164">Define a new exception type only if that type corresponds to a specific recovery strategy different from all of the existing exception types.</span></span> <span data-ttu-id="4d291-165">如果您非要确定义新的异常类型，则必须从 <xref:System.ServiceModel.CommunicationException> 或其派生类之一来派生该新类型。</span><span class="sxs-lookup"><span data-stu-id="4d291-165">If you do define a new exception type, it must derive from <xref:System.ServiceModel.CommunicationException> or one of its derived classes.</span></span>  
  
### <a name="exception-messages"></a><span data-ttu-id="4d291-166">异常消息</span><span class="sxs-lookup"><span data-stu-id="4d291-166">Exception Messages</span></span>  
 <span data-ttu-id="4d291-167">异常消息面向用户（而非程序），因此它们应提供足以帮助用户了解和解决问题的信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-167">Exception messages are targeted at the user not the program so they should provide sufficient information to help the user understand and solve the problem.</span></span> <span data-ttu-id="4d291-168">好的异常消息应包括以下三个基本部分：</span><span class="sxs-lookup"><span data-stu-id="4d291-168">The three essential parts of a good exception message are:</span></span>  
  
 <span data-ttu-id="4d291-169">所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="4d291-169">What happened.</span></span> <span data-ttu-id="4d291-170">使用与用户体验相关的术语明确说明问题所在。</span><span class="sxs-lookup"><span data-stu-id="4d291-170">Provide a clear description of the problem using terms that relate to the user’s experience.</span></span> <span data-ttu-id="4d291-171">例如，“Invalid configuration section”（配置节无效）是糟糕的异常消息。</span><span class="sxs-lookup"><span data-stu-id="4d291-171">For example, a bad exception message would be "Invalid configuration section".</span></span> <span data-ttu-id="4d291-172">这会令用户想知道哪个配置节有误以及它为何有误。</span><span class="sxs-lookup"><span data-stu-id="4d291-172">This leaves the user wondering which configuration section is incorrect and why it is incorrect.</span></span> <span data-ttu-id="4d291-173">改进的邮件将为"Invalid configuration section 节\<customBinding >"。</span><span class="sxs-lookup"><span data-stu-id="4d291-173">An improved message would be "Invalid configuration section \<customBinding>".</span></span> <span data-ttu-id="4d291-174">“Cannot add the transport named myTransport to the binding named myBinding because the binding already has a transport named myTransport”（无法将名为 myTransport 的传输添加到名为 myBinding 的绑定中，因为该绑定已经有一个名为 myTransport 的传输）是较好的消息。</span><span class="sxs-lookup"><span data-stu-id="4d291-174">An even better message would be "Cannot add the transport named myTransport to the binding named myBinding because the binding already has a transport named myTransport".</span></span> <span data-ttu-id="4d291-175">这个消息非常具体，用户可以在应用程序的配置文件中方便地标识该消息中所使用的术语和名称。</span><span class="sxs-lookup"><span data-stu-id="4d291-175">This is a very specific message using terms and names that the user can easily identify in the application’s configuration file.</span></span> <span data-ttu-id="4d291-176">但是，仍缺少几个关键部分。</span><span class="sxs-lookup"><span data-stu-id="4d291-176">However, there are still a few key components missing.</span></span>  
  
 <span data-ttu-id="4d291-177">错误的重要性。</span><span class="sxs-lookup"><span data-stu-id="4d291-177">The significance of the error.</span></span> <span data-ttu-id="4d291-178">除非该消息明确声明了错误的含义，否则用户很可能想知道它是否为致命错误，或者是否可以忽略它。</span><span class="sxs-lookup"><span data-stu-id="4d291-178">Unless the message states clearly what the error means, the user is likely to wonder whether it is a fatal error or if it can be ignored.</span></span> <span data-ttu-id="4d291-179">通常，消息中应首先声明错误的含义或重要性。</span><span class="sxs-lookup"><span data-stu-id="4d291-179">In general, messages should lead with the meaning or significance of the error.</span></span> <span data-ttu-id="4d291-180">为了改善上面的示例，可以将消息改为“ServiceHost failed to Open due to a configuration error: Cannot add the transport named myTransport to the binding named myBinding because the binding already has a transport named myTransport”（ServiceHost 因配置错误而未能打开: 无法将名为 myTransport 的传输添加到名为 myBinding 的绑定中，因为该绑定已经有一个名为 myTransport 的传输）。</span><span class="sxs-lookup"><span data-stu-id="4d291-180">To improve the previous example, the message could be "ServiceHost failed to Open due to a configuration error: Cannot add the transport named myTransport to the binding named myBinding because the binding already has a transport named myTransport".</span></span>  
  
 <span data-ttu-id="4d291-181">用户应如何更正问题。</span><span class="sxs-lookup"><span data-stu-id="4d291-181">How the user should correct the problem.</span></span> <span data-ttu-id="4d291-182">消息中最重要部分就是帮助用户修复问题。</span><span class="sxs-lookup"><span data-stu-id="4d291-182">The most important part of the message is helping the user fix the problem.</span></span> <span data-ttu-id="4d291-183">消息中应包括为纠正相关问题而需要检查或修复的内容的一些指南或提示。</span><span class="sxs-lookup"><span data-stu-id="4d291-183">The message should include some guidance or hints about what to check or fix to remedy the problem.</span></span> <span data-ttu-id="4d291-184">例如，“ServiceHost failed to Open due to a configuration error: Cannot add the transport named myTransport to the binding named myBinding because the binding already has a transport named myTransport.</span><span class="sxs-lookup"><span data-stu-id="4d291-184">For example, "ServiceHost failed to Open due to a configuration error: Cannot add the transport named myTransport to the binding named myBinding because the binding already has a transport named myTransport.</span></span> <span data-ttu-id="4d291-185">Please ensure there is only one transport in the binding”（ServiceHost 因配置错误而未能打开: 无法将名为 myTransport 的传输添加到名为 myBinding 的绑定中，因为该绑定已经有一个名为 myTransport 的传输。请确保该绑定中只有一个传输）。</span><span class="sxs-lookup"><span data-stu-id="4d291-185">Please ensure there is only one transport in the binding".</span></span>  
  
## <a name="communicating-faults"></a><span data-ttu-id="4d291-186">传达错误</span><span class="sxs-lookup"><span data-stu-id="4d291-186">Communicating Faults</span></span>  
 <span data-ttu-id="4d291-187">SOAP 1.1 和 SOAP 1.2 均为错误定义了一个特定的结构。</span><span class="sxs-lookup"><span data-stu-id="4d291-187">SOAP 1.1 and SOAP 1.2 both define a specific structure for faults.</span></span> <span data-ttu-id="4d291-188">这两个规范之间存在一些差异，但是，在创建和使用错误时通常使用 Message 和 MessageFault 类型。</span><span class="sxs-lookup"><span data-stu-id="4d291-188">There are some differences between the two specifications but in general, the Message and MessageFault types are used to create and consume faults.</span></span>  
  
 <span data-ttu-id="4d291-189">![处理异常和错误](../../../../docs/framework/wcf/extending/media/wcfc-soap1-1andsoap1-2faultcomparisonc.gif "wcfc_SOAP1 1AndSOAP1 2FaultComparisonc")</span><span class="sxs-lookup"><span data-stu-id="4d291-189">![Handling exceptions and faults](../../../../docs/framework/wcf/extending/media/wcfc-soap1-1andsoap1-2faultcomparisonc.gif "wcfc_SOAP1-1AndSOAP1-2FaultComparisonc")</span></span>  
<span data-ttu-id="4d291-190">SOAP 1.2 错误（左）和 SOAP 1.1 错误（右）。</span><span class="sxs-lookup"><span data-stu-id="4d291-190">SOAP 1.2 Fault (left) and SOAP 1.1 Fault (right).</span></span> <span data-ttu-id="4d291-191">请注意，在 SOAP 1.1 中，只有 Fault 元素受到命名空间的限定。</span><span class="sxs-lookup"><span data-stu-id="4d291-191">Note that in SOAP 1.1 only the Fault element is namespace qualified.</span></span>  
  
 <span data-ttu-id="4d291-192">SOAP 将错误消息定义为一个仅包含错误元素（名称为 `<env:Fault>` 的元素）的消息，该错误元素作为 `<env:Body>` 的子元素。</span><span class="sxs-lookup"><span data-stu-id="4d291-192">SOAP defines a fault message as a message that contains only a fault element (an element whose name is `<env:Fault>`) as a child of `<env:Body>`.</span></span> <span data-ttu-id="4d291-193">错误元素的内容在 SOAP 1.1 和 SOAP 1.2 之间略有不同，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="4d291-193">The contents of the fault element differ slightly between SOAP 1.1 and SOAP 1.2 as shown in figure 1.</span></span> <span data-ttu-id="4d291-194">但是，<xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType> 类会将这些差异标准化到一个对象模型中：</span><span class="sxs-lookup"><span data-stu-id="4d291-194">However, the <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType> class normalizes these differences into one object model:</span></span>  
  
```  
public abstract class MessageFault  
{  
    protected MessageFault();  
  
    public virtual string Actor { get; }  
    public virtual string Node { get; }  
    public static string DefaultAction { get; }  
    public abstract FaultCode Code { get; }  
    public abstract bool HasDetail { get; }  
    public abstract FaultReason Reason { get; }  
  
    public T GetDetail<T>();  
    public T GetDetail<T>( XmlObjectSerializer serializer);  
    public System.Xml.XmlDictionaryReader GetReaderAtDetailContents();  
  
    // other methods omitted  
}  
```  
  
 <span data-ttu-id="4d291-195">`Code` 属性对应于 `env:Code`（或 SOAP 1.1 中的 `faultCode`），可用来标识错误的类型。</span><span class="sxs-lookup"><span data-stu-id="4d291-195">The `Code` property corresponds to the `env:Code` (or `faultCode` in SOAP 1.1) and identifies the type of the fault.</span></span> <span data-ttu-id="4d291-196">SOAP 1.2 定义了五个 `faultCode` 所允许的值（例如，Sender（发送方）和 Receiver（接收方）），并定义了一个可以包含任何子代码值的 `Subcode` 元素</span><span class="sxs-lookup"><span data-stu-id="4d291-196">SOAP 1.2 defines five allowable values for `faultCode` (for example, Sender and Receiver) and defines a `Subcode` element which can contain any subcode value.</span></span> <span data-ttu-id="4d291-197">(请参阅[SOAP 1.2 规范](http://go.microsoft.com/fwlink/?LinkId=95176)有关允许的错误代码及其含义的列表。)SOAP 1.1 具有略微不同的机制：它定义了四个 `faultCode` 值（例如，Client（客户端）和 Server（服务器）），这些值可以通过定义全新的值来扩展，也可以通过使用点表示法来创建更具体的 `faultCodes`（例如，Client.Authentication）。</span><span class="sxs-lookup"><span data-stu-id="4d291-197">(See the [SOAP 1.2 specification](http://go.microsoft.com/fwlink/?LinkId=95176) for the list of allowable fault codes and their meaning.) SOAP 1.1 has a slightly different mechanism: It defines four `faultCode` values (for example, Client and Server) that can be extended either by defining entirely new ones or by using the dot notation to create more specific `faultCodes`, for example, Client.Authentication.</span></span>  
  
 <span data-ttu-id="4d291-198">在使用 MessageFault 对错误进行编程时，FaultCode.Name 和 FaultCode.Namespace 会映射到 `env:Code`（在 SOAP 1.2 中）或 `faultCode`（在 SOAP 1.1 中）的名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="4d291-198">When you use MessageFault to program faults, the FaultCode.Name and FaultCode.Namespace maps to the name and namespace of the SOAP 1.2 `env:Code` or the SOAP 1.1 `faultCode`.</span></span> <span data-ttu-id="4d291-199">FaultCode.SubCode 会映射到 `env:Subcode`（在 SOAP 1.2 中）或为 null（在 SOAP 1.1 中）。</span><span class="sxs-lookup"><span data-stu-id="4d291-199">The FaultCode.SubCode maps to `env:Subcode` for SOAP 1.2 and is null for SOAP 1.1.</span></span>  
  
 <span data-ttu-id="4d291-200">如果想要以编程方式区分某个错误，则应创建新的错误子代码（如果使用的是 SOAP 1.1，则应创建新的错误代码）。</span><span class="sxs-lookup"><span data-stu-id="4d291-200">You should create new fault subcodes (or new fault codes if using SOAP 1.1) if it is interesting to programmatically distinguish a fault.</span></span> <span data-ttu-id="4d291-201">这与创建新的异常类型相似。</span><span class="sxs-lookup"><span data-stu-id="4d291-201">This is analogous to creating a new exception type.</span></span> <span data-ttu-id="4d291-202">应避免在 SOAP 1.1 错误代码中使用点表示法</span><span class="sxs-lookup"><span data-stu-id="4d291-202">You should avoid using the dot notation with SOAP 1.1 fault codes.</span></span> <span data-ttu-id="4d291-203">( [WS-我的基本配置文件](http://go.microsoft.com/fwlink/?LinkId=95177)还不鼓励使用错误代码点表示法。)</span><span class="sxs-lookup"><span data-stu-id="4d291-203">(The [WS-I Basic Profile](http://go.microsoft.com/fwlink/?LinkId=95177) also discourages the use of the fault code dot notation.)</span></span>  
  
```  
public class FaultCode  
{  
    public FaultCode(string name);  
    public FaultCode(string name, FaultCode subCode);  
    public FaultCode(string name, string ns);  
    public FaultCode(string name, string ns, FaultCode subCode);  
  
    public bool IsPredefinedFault { get; }  
    public bool IsReceiverFault { get; }  
    public bool IsSenderFault { get; }  
    public string Name { get; }  
    public string Namespace { get; }  
    public FaultCode SubCode { get; }  
  
//  methods omitted  
  
}  
```  
  
 <span data-ttu-id="4d291-204">`Reason` 属性对应于 `env:Reason`（在 SOAP 1.1 中为 `faultString`），这是关于错误条件的可读说明，与异常消息相似。</span><span class="sxs-lookup"><span data-stu-id="4d291-204">The `Reason` property corresponds to the `env:Reason` (or `faultString` in SOAP 1.1) a human-readable description of the error condition analogous to an exception’s message.</span></span> <span data-ttu-id="4d291-205">`FaultReason` 类（和 SOAP `env:Reason/faultString`）对于为实现全球化而提供多种翻译具有内置的支持。</span><span class="sxs-lookup"><span data-stu-id="4d291-205">The `FaultReason` class (and SOAP `env:Reason/faultString`) has built-in support for having multiple translations in the interest of globalization.</span></span>  
  
```  
public class FaultReason  
{  
    public FaultReason(FaultReasonText translation);  
    public FaultReason(IEnumerable<FaultReasonText> translations);  
    public FaultReason(string text);  
  
    public SynchronizedReadOnlyCollection<FaultReasonText> Translations   
    {   
       get;   
    }  
  
 }  
```  
  
 <span data-ttu-id="4d291-206">错误详细信息内容公开在 MessageFault 上借助于各种方法包括`GetDetail` \<T > 和`GetReaderAtDetailContents`（)。</span><span class="sxs-lookup"><span data-stu-id="4d291-206">The fault detail contents are exposed on MessageFault using various methods including the `GetDetail`\<T> and `GetReaderAtDetailContents`().</span></span> <span data-ttu-id="4d291-207">错误详细信息是一个不透明的元素，其中包含有关错误的附加详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-207">The fault detail is an opaque element for carrying additional detail about the fault.</span></span> <span data-ttu-id="4d291-208">如果您希望错误中包含一些任意的结构化详细信息，则这非常有用。</span><span class="sxs-lookup"><span data-stu-id="4d291-208">This is useful if there is some arbitrary structured detail that you want to carry with the fault.</span></span>  
  
### <a name="generating-faults"></a><span data-ttu-id="4d291-209">生成错误</span><span class="sxs-lookup"><span data-stu-id="4d291-209">Generating Faults</span></span>  
 <span data-ttu-id="4d291-210">本节介绍为响应在通道中或通道所创建的消息属性中检测到的错误条件而生成错误的过程。</span><span class="sxs-lookup"><span data-stu-id="4d291-210">This section explains the process of generating a fault in response to an error condition detected in a channel or in a message property created by the channel.</span></span> <span data-ttu-id="4d291-211">典型的示例是发回错误以响应包含无效数据的请求消息。</span><span class="sxs-lookup"><span data-stu-id="4d291-211">A typical example is sending back a fault in response to a request message that contains invalid data.</span></span>  
  
 <span data-ttu-id="4d291-212">在生成错误时，自定义通道不应直接发送错误，而是应引发异常，并让上一层决定是否将该异常转换为错误以及如何发送它。</span><span class="sxs-lookup"><span data-stu-id="4d291-212">When generating a fault, the custom channel should not send the fault directly, rather, it should throw an exception and let the layer above decide whether to convert that exception to a fault and how to send it.</span></span> <span data-ttu-id="4d291-213">为了帮助进行此转换，该通道应提供一个 `FaultConverter` 实现，以便可以将自定义通道所引发的异常转换为相应的错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-213">To aid in this conversion, the channel should provide a `FaultConverter` implementation that can convert the exception thrown by the custom channel to the appropriate fault.</span></span> <span data-ttu-id="4d291-214">`FaultConverter` 定义为：</span><span class="sxs-lookup"><span data-stu-id="4d291-214">`FaultConverter` is defined as:</span></span>  
  
```  
public class FaultConverter  
{  
    public static FaultConverter GetDefaultFaultConverter(  
                                   MessageVersion version);  
    protected abstract bool OnTryCreateFaultMessage(  
                                   Exception exception,   
                                   out Message message);  
    public bool TryCreateFaultMessage(  
                                   Exception exception,   
                                   out Message message);  
}  
```  
  
 <span data-ttu-id="4d291-215">用来生成自定义错误的每个通道都必须实现 `FaultConverter` 并通过调用 `GetProperty<FaultConverter>` 来返回它。</span><span class="sxs-lookup"><span data-stu-id="4d291-215">Each channel that generates custom faults must implement `FaultConverter` and return it from a call to `GetProperty<FaultConverter>`.</span></span> <span data-ttu-id="4d291-216">自定义 `OnTryCreateFaultMessage` 实现必须将异常转换为错误或者将异常委托给内部通道的 `FaultConverter`。</span><span class="sxs-lookup"><span data-stu-id="4d291-216">The custom `OnTryCreateFaultMessage` implementation must either convert the exception to a fault or delegate to the inner channel’s `FaultConverter`.</span></span> <span data-ttu-id="4d291-217">如果通道是传输它必须将异常转换，或将委托给编码器的`FaultConverter`或默认值`FaultConverter`WCF 中提供。</span><span class="sxs-lookup"><span data-stu-id="4d291-217">If the channel is a transport it must either convert the exception or delegate to the encoder’s `FaultConverter` or the default `FaultConverter` provided in WCF .</span></span> <span data-ttu-id="4d291-218">默认的 `FaultConverter` 会转换与 WS-Addressing 和 SOAP 所指定的错误消息相对应的错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-218">The default `FaultConverter` converts errors corresponding to fault messages specified by WS-Addressing and SOAP.</span></span> <span data-ttu-id="4d291-219">下面是一个示例 `OnTryCreateFaultMessage` 实现。</span><span class="sxs-lookup"><span data-stu-id="4d291-219">Here is an example `OnTryCreateFaultMessage` implementation.</span></span>  
  
```  
public override bool OnTryCreateFaultMessage(Exception exception,   
                                             out Message message)  
{  
    if (exception is ...)  
    {  
        message = ...;  
        return true;  
    }  
  
#if IMPLEMENTING_TRANSPORT_CHANNEL  
    FaultConverter encoderConverter =   
                    this.encoder.GetProperty<FaultConverter>();  
    if ((encoderConverter != null) &&               
        (encoderConverter.TryCreateFaultMessage(  
         exception, out message)))  
    {  
        return true;  
    }  
  
    FaultConverter defaultConverter =   
                   FaultConverter.GetDefaultFaultConverter(  
                   this.channel.messageVersion);  
    return defaultConverter.TryCreateFaultMessage(  
                   exception,   
                   out message);  
#else  
    FaultConverter inner =   
                   this.innerChannel.GetProperty<FaultConverter>();  
    if (inner != null)  
    {  
        return inner.TryCreateFaultMessage(exception, out message);  
    }  
    else  
    {  
        message = null;  
        return false;  
    }  
#endif  
}  
```  
  
 <span data-ttu-id="4d291-220">此模式的含意为，在各层之间针对那些要求错误的错误条件而引发的异常必须包含足够的信息，以使相应的错误生成器能创建正确的错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-220">An implication of this pattern is that exceptions thrown between layers for error conditions that require faults must contain enough information for the corresponding fault generator to create the correct fault.</span></span> <span data-ttu-id="4d291-221">自定义通道的作者可以定义与不同错误条件相对应的异常类型（如果此类异常还不存在）。</span><span class="sxs-lookup"><span data-stu-id="4d291-221">As a custom channel author, you may define exception types that correspond to different fault conditions if such exceptions do not already exist.</span></span> <span data-ttu-id="4d291-222">请注意，穿越通道层的异常应传达错误条件（而非不透明的错误数据）。</span><span class="sxs-lookup"><span data-stu-id="4d291-222">Note that exceptions traversing channel layers should communicate the error condition rather than opaque fault data.</span></span>  
  
### <a name="fault-categories"></a><span data-ttu-id="4d291-223">错误类别</span><span class="sxs-lookup"><span data-stu-id="4d291-223">Fault Categories</span></span>  
 <span data-ttu-id="4d291-224">通常有三种类别的错误：</span><span class="sxs-lookup"><span data-stu-id="4d291-224">There are generally three categories of faults:</span></span>  
  
1.  <span data-ttu-id="4d291-225">遍布整个堆栈的错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-225">Faults that are pervasive throughout the entire stack.</span></span> <span data-ttu-id="4d291-226">在通道堆栈中的任何一层都有可能遇到这些错误（如，InvalidCardinalityAddressingException）。</span><span class="sxs-lookup"><span data-stu-id="4d291-226">These faults could be encountered at any layer in the channel stack, for example InvalidCardinalityAddressingException.</span></span>  
  
2.  <span data-ttu-id="4d291-227">可能会在堆栈中某层之上的任何一层遇到的错误，例如，与流事务或安全角色相关的某些错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-227">Faults that can be encountered anywhere above a certain layer in the stack for example some errors that pertain to a flowed transaction or to security roles.</span></span>  
  
3.  <span data-ttu-id="4d291-228">针对堆栈中单个层的错误，例如，像 WS-RM 序列号错误之类的错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-228">Faults that are directed at a single layer in the stack, for example errors like WS-RM sequence number faults.</span></span>  
  
 <span data-ttu-id="4d291-229">类别 1。</span><span class="sxs-lookup"><span data-stu-id="4d291-229">Category 1.</span></span> <span data-ttu-id="4d291-230">的错误通常是 WS-Addressing 和 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-230">Faults are generally WS-Addressing and SOAP faults.</span></span> <span data-ttu-id="4d291-231">基`FaultConverter`类提供由 WCF 将错误消息相对应的错误指定的 Ws-addressing 和 SOAP 因此你不必处理这些异常的转换自己。</span><span class="sxs-lookup"><span data-stu-id="4d291-231">The base `FaultConverter` class provided by WCF converts errors corresponding to fault messages specified by WS-Addressing and SOAP so you do not have to handle conversion of these exceptions yourself.</span></span>  
  
 <span data-ttu-id="4d291-232">类别 2。</span><span class="sxs-lookup"><span data-stu-id="4d291-232">Category 2.</span></span> <span data-ttu-id="4d291-233">的错误在以下情况下出现：某个层向消息中添加一个属性，而该消息不完全使用与此层有关的消息信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-233">Faults occur when a layer adds a property to the message that does not completely consume message information that pertains to that layer.</span></span> <span data-ttu-id="4d291-234">当高层以后请求消息属性进一步处理消息信息时，则可能会检测到错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-234">Errors may be detected later when a higher layer asks the message property to process message information further.</span></span> <span data-ttu-id="4d291-235">这样的通道应实现以前指定的 `GetProperty`，以使高层可以发回正确的错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-235">Such channels should implement the `GetProperty` specified previously to enable the higher layer to send back the correct fault.</span></span> <span data-ttu-id="4d291-236">TransactionMessageProperty 就是这方面的一个示例。</span><span class="sxs-lookup"><span data-stu-id="4d291-236">An example of this is the TransactionMessageProperty.</span></span> <span data-ttu-id="4d291-237">此属性会添加到消息中，而不会完全验证标头中的所有数据（完全验证可能涉及到与分布式事务处理协调器 (DTC) 联系）。</span><span class="sxs-lookup"><span data-stu-id="4d291-237">This property is added to the message without fully validating all the data in the header (doing so may involve contacting the distributed transaction coordinator (DTC).</span></span>  
  
 <span data-ttu-id="4d291-238">属于类别 3</span><span class="sxs-lookup"><span data-stu-id="4d291-238">Category 3.</span></span> <span data-ttu-id="4d291-239">的错误仅通过处理器中的单个层来生成和发送。</span><span class="sxs-lookup"><span data-stu-id="4d291-239">Faults are only generated and sent by a single layer in the processor.</span></span> <span data-ttu-id="4d291-240">因此，所有的异常都包含在该层中。</span><span class="sxs-lookup"><span data-stu-id="4d291-240">Therefore all the exceptions are contained within the layer.</span></span> <span data-ttu-id="4d291-241">为了提高通道之间的一致性和维护方便性，自定义通道应使用以前指定的模式来生成错误消息，即使对于内部错误也是如此。</span><span class="sxs-lookup"><span data-stu-id="4d291-241">To improve consistency among channels and ease maintenance, your custom channel should use the pattern specified previously to generate fault messages even for internal faults.</span></span>  
  
### <a name="interpreting-received-faults"></a><span data-ttu-id="4d291-242">解释收到的错误</span><span class="sxs-lookup"><span data-stu-id="4d291-242">Interpreting Received Faults</span></span>  
 <span data-ttu-id="4d291-243">本节提供关于接收错误消息时生成相应异常的指南。</span><span class="sxs-lookup"><span data-stu-id="4d291-243">This section provides guidance for generating the appropriate exception when receiving a fault message.</span></span> <span data-ttu-id="4d291-244">下面是用来在堆栈中的每一层处理消息的决策树：</span><span class="sxs-lookup"><span data-stu-id="4d291-244">The decision tree for processing a message at every layer in the stack is as follows:</span></span>  
  
1.  <span data-ttu-id="4d291-245">如果该层认为消息无效，则该层应进行“无效消息”处理。</span><span class="sxs-lookup"><span data-stu-id="4d291-245">If the layer considers the message to be invalid, the layer should do its ‘invalid message’ processing.</span></span> <span data-ttu-id="4d291-246">此类处理特定于该层，但是可以包括丢弃消息、跟踪或引发已转换为错误的异常。</span><span class="sxs-lookup"><span data-stu-id="4d291-246">Such processing is specific to the layer but could include dropping the message, tracing, or throwing an exception that gets converted to a fault.</span></span> <span data-ttu-id="4d291-247">这方面的示例包括对未正确保护的消息的安全接收，或者对序列号有误的消息的 RM 接收。</span><span class="sxs-lookup"><span data-stu-id="4d291-247">Examples include security receiving a message that is not secured properly, or RM receiving a message with a bad sequence number.</span></span>  
  
2.  <span data-ttu-id="4d291-248">否则，如果此消息是该层特有的错误消息，而且此消息在该层的交互外部没有意义，则该层应处理错误条件。</span><span class="sxs-lookup"><span data-stu-id="4d291-248">Otherwise, if the message is a fault message that applies specifically to the layer, and the message is not meaningful outside the layer’s interaction, the layer should handle the error condition.</span></span> <span data-ttu-id="4d291-249">这方面的示例包括“RM 序列被拒绝”错误，这类错误对于 RM 通道上方的各层没有意义，表示从挂起操作引发的 RM 通道错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-249">An example of this is an RM Sequence Refused fault that is meaningless to layers above the RM channel and that implies faulting the RM channel and throwing from pending operations.</span></span>  
  
3.  <span data-ttu-id="4d291-250">否则，该消息应从 Request() 或 Receive() 返回。</span><span class="sxs-lookup"><span data-stu-id="4d291-250">Otherwise, the message should be returned from Request() or Receive().</span></span> <span data-ttu-id="4d291-251">这包括如下情况：该层能够识别此错误，但是此错误仅指示请求失败，而不表示从挂起操作引发的通道错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-251">This includes cases where the layer recognizes the fault, but the fault just indicates that a request failed and does not imply faulting the channel and throwing from pending operations.</span></span> <span data-ttu-id="4d291-252">若要在类似情况下提高可用性，该层应实现 `GetProperty<FaultConverter>`，并返回一个可以通过重写 `FaultConverter` 将错误转换为异常的 `OnTryCreateException` 派生类。</span><span class="sxs-lookup"><span data-stu-id="4d291-252">To improve usability in such a case, the layer should implement `GetProperty<FaultConverter>` and return a `FaultConverter` derived class that can convert the fault to an exception by overriding `OnTryCreateException`.</span></span>  
  
 <span data-ttu-id="4d291-253">下面的对象模型支持将消息转换为异常：</span><span class="sxs-lookup"><span data-stu-id="4d291-253">The following object model supports converting messages to exceptions:</span></span>  
  
```  
public class FaultConverter  
{  
    public static FaultConverter GetDefaultFaultConverter(  
                                  MessageVersion version);  
    protected abstract bool OnTryCreateException(  
                                 Message message,   
                                 MessageFault fault,   
                                 out Exception exception);  
    public bool TryCreateException(  
                                 Message message,   
                                 MessageFault fault,   
                                 out Exception exception);  
}  
```  
  
 <span data-ttu-id="4d291-254">通道层可以实现 `GetProperty<FaultConverter>` 来支持将错误消息转换为异常。</span><span class="sxs-lookup"><span data-stu-id="4d291-254">A channel layer can implement `GetProperty<FaultConverter>` to support converting fault messages to exceptions.</span></span> <span data-ttu-id="4d291-255">为此，需要重写 `OnTryCreateException` 并检查错误消息。</span><span class="sxs-lookup"><span data-stu-id="4d291-255">To do so, override `OnTryCreateException` and inspect the fault message.</span></span> <span data-ttu-id="4d291-256">如果识别出错误消息，请执行转换，否则可以让内部通道转换它。</span><span class="sxs-lookup"><span data-stu-id="4d291-256">If recognized, do the conversion, otherwise ask the inner channel to convert it.</span></span> <span data-ttu-id="4d291-257">传输通道应委托给 `FaultConverter.GetDefaultFaultConverter`，以便获取默认的 SOAP/WS-Addressing FaultConverter。</span><span class="sxs-lookup"><span data-stu-id="4d291-257">Transport channels should delegate to `FaultConverter.GetDefaultFaultConverter` to get the default SOAP/WS-Addressing FaultConverter.</span></span>  
  
 <span data-ttu-id="4d291-258">典型的实现应如下所示：</span><span class="sxs-lookup"><span data-stu-id="4d291-258">A typical implementation looks like this:</span></span>  
  
```  
public override bool OnTryCreateException(  
                            Message message,   
                            MessageFault fault,   
                            out Exception exception)  
{  
    if (message.Action == "...")  
    {  
        exception = ...;  
        return true;  
    }  
    // OR  
    if ((fault.Code.Name == "...") && (fault.Code.Namespace == "..."))  
    {  
        exception = ...;  
        return true;  
    }  
  
    if (fault.IsMustUnderstand)  
    {  
        if (fault.WasHeaderNotUnderstood(  
                   message.Headers, "...", "..."))  
        {  
            exception = new ProtocolException(...);  
            return true;  
        }  
    }  
  
#if IMPLEMENTING_TRANSPORT_CHANNEL  
    FaultConverter encoderConverter =   
              this.encoder.GetProperty<FaultConverter>();  
    if ((encoderConverter != null) &&   
        (encoderConverter.TryCreateException(  
                              message, fault, out exception)))  
    {  
        return true;  
    }  
  
    FaultConverter defaultConverter =  
             FaultConverter.GetDefaultFaultConverter(  
                             this.channel.messageVersion);  
    return defaultConverter.TryCreateException(  
                             message, fault, out exception);  
#else  
    FaultConverter inner =   
                    this.innerChannel.GetProperty<FaultConverter>();  
    if (inner != null)  
    {  
        return inner.TryCreateException(message, fault, out exception);  
    }  
    else  
    {  
        exception = null;  
        return false;  
    }  
#endif  
}  
```  
  
 <span data-ttu-id="4d291-259">对于具有不同恢复方案的特定错误条件，请考虑定义 `ProtocolException` 的派生类。</span><span class="sxs-lookup"><span data-stu-id="4d291-259">For specific fault conditions that have distinct recovery scenarios, consider defining a derived class of `ProtocolException`.</span></span>  
  
### <a name="mustunderstand-processing"></a><span data-ttu-id="4d291-260">MustUnderstand 处理</span><span class="sxs-lookup"><span data-stu-id="4d291-260">MustUnderstand Processing</span></span>  
 <span data-ttu-id="4d291-261">SOAP 定义一个用于指示接收方未理解必需的标头的通用错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-261">SOAP defines a general fault for signaling that a required header was not understood by the receiver.</span></span> <span data-ttu-id="4d291-262">此错误称为 `mustUnderstand` 错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-262">This fault is known as the `mustUnderstand` fault.</span></span> <span data-ttu-id="4d291-263">在 WCF 中，自定义通道永远不会生成`mustUnderstand`错误。</span><span class="sxs-lookup"><span data-stu-id="4d291-263">In WCF, custom channels never generate `mustUnderstand` faults.</span></span> <span data-ttu-id="4d291-264">相反，位于 WCF 通信堆栈的顶部，WCF 调度程序会检查的所有标头的了标记为 MustUndestand = true 基础堆栈是否理解。</span><span class="sxs-lookup"><span data-stu-id="4d291-264">Instead, the WCF Dispatcher, which is located at the top of the WCF communication stack, checks to see that all headers that were marked as MustUndestand=true were understood by the underlying stack.</span></span> <span data-ttu-id="4d291-265">如果均未理解，则此时会生成一个 `mustUnderstand` 错误</span><span class="sxs-lookup"><span data-stu-id="4d291-265">If any were not understood, a `mustUnderstand` fault is generated at that point.</span></span> <span data-ttu-id="4d291-266">（用户可以选择关闭此 `mustUnderstand` 处理，并让应用程序接收所有消息头。</span><span class="sxs-lookup"><span data-stu-id="4d291-266">(The user can choose to turn off this `mustUnderstand` processing and have the application receive all message headers.</span></span> <span data-ttu-id="4d291-267">在这种情况下，应用程序负责执行 `mustUnderstand` 处理)。所生成的错误包括一个 NotUnderstood 标头，其中包含未理解且 MustUnderstand=true 的所有标头的名称。</span><span class="sxs-lookup"><span data-stu-id="4d291-267">In that case the application is responsible for performing `mustUnderstand` processing.) The generated fault includes a NotUnderstood header that contains the names of all headers with MustUnderstand=true that were not understood.</span></span>  
  
 <span data-ttu-id="4d291-268">如果协议通道发送一个 MustUnderstand=true 的自定义标头，并收到一个 `mustUnderstand` 错误，则这个协议通道必须确定该错误是否起因它所发送的标头。</span><span class="sxs-lookup"><span data-stu-id="4d291-268">If your protocol channel sends a custom header with MustUnderstand=true and receives a `mustUnderstand` fault, it must figure out whether that fault is due to the header it sent.</span></span> <span data-ttu-id="4d291-269">`MessageFault` 类有两个可用来执行此操作的成员：</span><span class="sxs-lookup"><span data-stu-id="4d291-269">There are two members on the `MessageFault` class that are useful for this:</span></span>  
  
```  
public class MessageFault  
{  
    ...  
    public bool IsMustUnderstandFault { get; }  
    public static bool WasHeaderNotUnderstood(MessageHeaders headers,   
        string name, string ns) { }  
    ...  
  
}  
```  
  
 <span data-ttu-id="4d291-270">如果故障是 `IsMustUnderstandFault` 故障，`true` 返回 `mustUnderstand`。</span><span class="sxs-lookup"><span data-stu-id="4d291-270">`IsMustUnderstandFault` returns `true` if the fault is a `mustUnderstand` fault.</span></span> <span data-ttu-id="4d291-271">如果具有指定名称和命名空间的标头以 NotUnderstood 标头的形式包括在该错误中，则 `WasHeaderNotUnderstood` 将返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="4d291-271">`WasHeaderNotUnderstood` returns `true` if the header with the specified name and namespace is included in the fault as a NotUnderstood header.</span></span>  <span data-ttu-id="4d291-272">否则，它将返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="4d291-272">Otherwise, it returns `false`.</span></span>  
  
 <span data-ttu-id="4d291-273">如果某个通道发出一个带有 MustUnderstand = true 标记的标头，则该层还应实现异常生成 API 模式，而且应按照前面的说明将该头所引起的 `mustUnderstand` 错误转换为更为有用的异常。</span><span class="sxs-lookup"><span data-stu-id="4d291-273">If a channel emits a header that is marked MustUnderstand = true, then that layer should also implement the Exception Generation API pattern and should convert `mustUnderstand` faults caused by that header to a more useful exception as described previously.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="4d291-274">跟踪</span><span class="sxs-lookup"><span data-stu-id="4d291-274">Tracing</span></span>  
 <span data-ttu-id="4d291-275">.NET Framework 提供了一种用来跟踪程序执行情况的机制，使用此机制，可以在无法简单地附加一个调试器并逐句通过代码时帮助诊断成品应用程序或中间问题。</span><span class="sxs-lookup"><span data-stu-id="4d291-275">The .NET Framework provides a mechanism to trace program execution as a way to aid diagnosing production applications or intermittent problems where it is not possible to just attach a debugger and step through the code.</span></span> <span data-ttu-id="4d291-276">此机制的核心组件位于 <xref:System.Diagnostics?displayProperty=nameWithType> 命名空间中，此机制中包含下列组件：</span><span class="sxs-lookup"><span data-stu-id="4d291-276">The core components of this mechanism are in the <xref:System.Diagnostics?displayProperty=nameWithType> namespace and consist of:</span></span>  
  
-   <span data-ttu-id="4d291-277"><xref:System.Diagnostics.TraceSource?displayProperty=nameWithType>（要写入的跟踪信息的源）、<xref:System.Diagnostics.TraceListener?displayProperty=nameWithType>（具体侦听器的抽象基类，具体侦听器接收要从 <xref:System.Diagnostics.TraceSource> 跟踪的信息并将其输出到侦听器特定的目标，</span><span class="sxs-lookup"><span data-stu-id="4d291-277"><xref:System.Diagnostics.TraceSource?displayProperty=nameWithType>, which is the source of trace information to be written, <xref:System.Diagnostics.TraceListener?displayProperty=nameWithType>, which is an abstract base class for concrete listeners that receive the information to be traced from the <xref:System.Diagnostics.TraceSource> and output it to a listener-specific destination.</span></span> <span data-ttu-id="4d291-278">例如，<xref:System.Diagnostics.XmlWriterTraceListener> 将跟踪信息输出到 XML 文件中。)</span><span class="sxs-lookup"><span data-stu-id="4d291-278">For example, <xref:System.Diagnostics.XmlWriterTraceListener> outputs trace information to an XML file.</span></span> <span data-ttu-id="4d291-279">以及 <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>（允许应用程序用户控制跟踪的详细级别，通常在配置中指定）。</span><span class="sxs-lookup"><span data-stu-id="4d291-279">Finally, <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType>, which lets the application user control the tracing verbosity and is typically specified in configuration.</span></span>  
  
-   <span data-ttu-id="4d291-280">除了的核心组件，你可以使用[服务跟踪查看器工具 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)查看和搜索 WCF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="4d291-280">In addition to the core components, you can use the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) to view and search WCF traces.</span></span> <span data-ttu-id="4d291-281">该工具专为跟踪文件生成的 WCF 和写出使用设计<xref:System.Diagnostics.XmlWriterTraceListener>。</span><span class="sxs-lookup"><span data-stu-id="4d291-281">The tool is designed specifically for trace files generated by WCF and written out using <xref:System.Diagnostics.XmlWriterTraceListener>.</span></span> <span data-ttu-id="4d291-282">下图演示了跟踪中涉及到的各种组件。</span><span class="sxs-lookup"><span data-stu-id="4d291-282">The following figure shows the various components involved in tracing.</span></span>  
  
 <span data-ttu-id="4d291-283">![处理异常和错误](../../../../docs/framework/wcf/extending/media/wcfc-tracinginchannelsc.gif "wcfc_TracingInChannelsc")</span><span class="sxs-lookup"><span data-stu-id="4d291-283">![Handling exceptions and faults](../../../../docs/framework/wcf/extending/media/wcfc-tracinginchannelsc.gif "wcfc_TracingInChannelsc")</span></span>  
  
### <a name="tracing-from-a-custom-channel"></a><span data-ttu-id="4d291-284">从自定义通道跟踪</span><span class="sxs-lookup"><span data-stu-id="4d291-284">Tracing from a Custom Channel</span></span>  
 <span data-ttu-id="4d291-285">自定义通道应写出跟踪消息，以便在无法向正在运行的应用程序附加调试器时帮助诊断问题。</span><span class="sxs-lookup"><span data-stu-id="4d291-285">Custom channels should write out trace messages to assist in diagnosing problems when it is not possible to attach a debugger to the running application.</span></span> <span data-ttu-id="4d291-286">这涉及到两个高级任务：实例化 <xref:System.Diagnostics.TraceSource> 和调用其方法来写入跟踪。</span><span class="sxs-lookup"><span data-stu-id="4d291-286">This involves two high level tasks: Instantiating a <xref:System.Diagnostics.TraceSource> and calling its methods to write traces.</span></span>  
  
 <span data-ttu-id="4d291-287">在实例化 <xref:System.Diagnostics.TraceSource> 时，所指定的字符串将成为该源的名称。</span><span class="sxs-lookup"><span data-stu-id="4d291-287">When instantiating a <xref:System.Diagnostics.TraceSource>, the string you specify becomes the name of that source.</span></span> <span data-ttu-id="4d291-288">此名称用来配置（启用/禁用/设置跟踪级别）跟踪源。</span><span class="sxs-lookup"><span data-stu-id="4d291-288">This name is used to configure (enable/disable/set tracing level) the trace source.</span></span> <span data-ttu-id="4d291-289">此名称还显示在跟踪输出本身当中。</span><span class="sxs-lookup"><span data-stu-id="4d291-289">It also appears in the trace output itself.</span></span> <span data-ttu-id="4d291-290">自定义通道应使用唯一的源名称来帮助该跟踪输出的读取器了解跟踪信息的出处。</span><span class="sxs-lookup"><span data-stu-id="4d291-290">Custom channels should use a unique source name to help readers of the trace output understand where the trace information comes from.</span></span> <span data-ttu-id="4d291-291">常见的做法是将正在写入信息的程序集的名称用作跟踪源的名称。</span><span class="sxs-lookup"><span data-stu-id="4d291-291">Using the name of the assembly that is writing the information as the name of the trace source is the common practice.</span></span> <span data-ttu-id="4d291-292">例如，WCF 用作 System.ServiceModel 跟踪源写入从 System.ServiceModel 程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="4d291-292">For example, WCF uses System.ServiceModel as the trace source for information written from the System.ServiceModel assembly.</span></span>  
  
 <span data-ttu-id="4d291-293">有了跟踪源之后，就可以调用它的 <xref:System.Diagnostics.TraceSource.TraceData%2A>、<xref:System.Diagnostics.TraceSource.TraceEvent%2A> 或 <xref:System.Diagnostics.TraceSource.TraceInformation%2A> 方法将跟踪项写入跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="4d291-293">Once you have a trace source, you call its <xref:System.Diagnostics.TraceSource.TraceData%2A>, <xref:System.Diagnostics.TraceSource.TraceEvent%2A>, or <xref:System.Diagnostics.TraceSource.TraceInformation%2A> methods to write trace entries to the trace listeners.</span></span> <span data-ttu-id="4d291-294">对于所写入的每个跟踪项，需要将事件归为 <xref:System.Diagnostics.TraceEventType> 中所定义的事件类型之一。</span><span class="sxs-lookup"><span data-stu-id="4d291-294">For each trace entry you write, you need to classify the type of event as one of the event types defined in <xref:System.Diagnostics.TraceEventType>.</span></span> <span data-ttu-id="4d291-295">是否将跟踪项输出到侦听器取决于该分类以及配置中的跟踪级别设置。</span><span class="sxs-lookup"><span data-stu-id="4d291-295">This classification and the trace level setting in configuration determine whether the trace entry is output to the listener.</span></span> <span data-ttu-id="4d291-296">例如，如果将配置中的跟踪级别设置为 `Warning`，则将允许写入 `Warning`、`Error` 和 `Critical` 跟踪项，但会阻止 Information（信息）和 Verbose（详细）项。</span><span class="sxs-lookup"><span data-stu-id="4d291-296">For example, setting the trace level in configuration to `Warning` allows `Warning`, `Error` and `Critical` trace entries to be written but blocks Information and Verbose entries.</span></span> <span data-ttu-id="4d291-297">下面的示例关于在 Information（信息）级别实例化跟踪源和写出项：</span><span class="sxs-lookup"><span data-stu-id="4d291-297">Here is an example of instantiating a trace source and writing out an entry at Information level:</span></span>  
  
```  
using System.Diagnostics;  
//...  
TraceSource udpSource=new TraceSource("Microsoft.Samples.Udp");  
//...  
udpsource.TraceInformation("UdpInputChannel received a message");  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="4d291-298">强烈建议您指定一个对于自定义通道保持唯一的跟踪源名称，以帮助跟踪输出读取器了解该输出的出处。</span><span class="sxs-lookup"><span data-stu-id="4d291-298">It is highly recommended that you specify a trace source name that is unique to your custom channel to help trace output readers understand where the output came from.</span></span>  
  
#### <a name="integrating-with-the-trace-viewer"></a><span data-ttu-id="4d291-299">与跟踪查看器集成</span><span class="sxs-lookup"><span data-stu-id="4d291-299">Integrating with the Trace Viewer</span></span>  
 <span data-ttu-id="4d291-300">由您的通道生成的跟踪可能会通过可读格式输出[服务跟踪查看器工具 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)使用<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>作为跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="4d291-300">Traces generated by your channel can be output in a format readable by the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) by using <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> as the trace listener.</span></span> <span data-ttu-id="4d291-301">此操作无需由通道开发人员来执行，</span><span class="sxs-lookup"><span data-stu-id="4d291-301">This is not something you, as the channel developer, need to do.</span></span> <span data-ttu-id="4d291-302">而是应由应用程序用户（或者对应用程序进行疑难解答的人员）在应用程序的配置文件中配置该跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="4d291-302">Rather, it is the application user (or the person troubleshooting the application) that needs to configure this trace listener in the application’s configuration file.</span></span> <span data-ttu-id="4d291-303">例如，下面的配置将 <xref:System.ServiceModel?displayProperty=nameWithType> 和 `Microsoft.Samples.Udp` 中的跟踪信息均输出到名为 `TraceEventsFile.e2e` 的文件中：</span><span class="sxs-lookup"><span data-stu-id="4d291-303">For example, the following configuration outputs trace information from both <xref:System.ServiceModel?displayProperty=nameWithType> and `Microsoft.Samples.Udp` to the file named `TraceEventsFile.e2e`:</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <!-- configure System.ServiceModel trace source -->  
      <source name="System.ServiceModel" switchValue="Verbose"   
              propagateActivity="true">  
        <listeners>  
          <add name="e2e" />  
        </listeners>  
      </source>  
      <!-- configure Microsoft.Samples.Udp trace source -->  
      <source name="Microsoft.Samples.Udp" switchValue="Verbose" >  
        <listeners>  
          <add name="e2e" />  
        </listeners>  
      </source>  
    </sources>  
    <!--   
    Define a shared trace listener that outputs to TraceFile.e2e  
    The listener name is e2e   
    -->  
    <sharedListeners>  
      <add name="e2e" type="System.Diagnostics.XmlWriterTraceListener"  
        initializeData=".\TraceFile.e2e"/>  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
</configuration>  
```  
  
#### <a name="tracing-structured-data"></a><span data-ttu-id="4d291-304">跟踪结构化数据</span><span class="sxs-lookup"><span data-stu-id="4d291-304">Tracing Structured Data</span></span>  
 <span data-ttu-id="4d291-305"><xref:System.Diagnostics.TraceSource?displayProperty=nameWithType> 具有一个 <xref:System.Diagnostics.TraceSource.TraceData%2A> 方法，该方法采用一个或多个要包括在跟踪项中的对象。</span><span class="sxs-lookup"><span data-stu-id="4d291-305"><xref:System.Diagnostics.TraceSource?displayProperty=nameWithType> has a <xref:System.Diagnostics.TraceSource.TraceData%2A> method that takes one or more objects that are to be included in the trace entry.</span></span> <span data-ttu-id="4d291-306">通常，会在每个对象上调用 <xref:System.Object.ToString%2A?displayProperty=nameWithType> 方法，而且所生成的字符串会作为跟踪项的一部分来写入。</span><span class="sxs-lookup"><span data-stu-id="4d291-306">In general, the <xref:System.Object.ToString%2A?displayProperty=nameWithType> method is called on each object and the resulting string is written as part of the trace entry.</span></span> <span data-ttu-id="4d291-307">在使用 <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> 来输出跟踪内容时，可以将 <xref:System.Xml.XPath.IXPathNavigable?displayProperty=nameWithType> 作为数据对象传递给 <xref:System.Diagnostics.TraceSource.TraceData%2A>。</span><span class="sxs-lookup"><span data-stu-id="4d291-307">When using <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> to output traces, you can pass an <xref:System.Xml.XPath.IXPathNavigable?displayProperty=nameWithType> as the data object to <xref:System.Diagnostics.TraceSource.TraceData%2A>.</span></span> <span data-ttu-id="4d291-308">所生成的跟踪项包括由 <xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType> 提供的 XML。</span><span class="sxs-lookup"><span data-stu-id="4d291-308">The resulting trace entry includes the XML provided by the <xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4d291-309">下面是 XML 应用程序数据的示例项：</span><span class="sxs-lookup"><span data-stu-id="4d291-309">Here is an example entry with XML application data:</span></span>  
  
```xml  
<E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">  
  <System xmlns="...">  
    <EventID>12</EventID>  
    <Type>3</Type>  
    <SubType Name="Information">0</SubType>  
    <Level>8</Level>  
    <TimeCreated SystemTime="2006-01-13T22:58:03.0654832Z" />  
    <Source Name="Microsoft.ServiceModel.Samples.Udp" />  
    <Correlation ActivityID="{00000000-0000-0000-0000-000000000000}" />  
    <Execution  ProcessName="UdpTestConsole"   
                ProcessID="3348" ThreadID="4" />  
    <Channel />  
    <Computer>COMPUTER-LT01</Computer>  
  </System>  
<!-- XML application data -->  
  <ApplicationData>  
  <TraceData>  
   <DataItem>  
   <TraceRecord   
     Severity="Information"  
     xmlns="…">  
        <TraceIdentifier>some trace id</TraceIdentifier>  
        <Description>EndReceive called</Description>  
        <AppDomain>UdpTestConsole.exe</AppDomain>  
        <Source>UdpInputChannel</Source>  
      </TraceRecord>  
    </DataItem>  
  </TraceData>  
  </ApplicationData>  
</E2ETraceEvent>  
```  
  
 <span data-ttu-id="4d291-310">WCF 跟踪查看器理解的架构`TraceRecord`如前面所述的元素和从其子元素中提取数据并以表格格式显示。</span><span class="sxs-lookup"><span data-stu-id="4d291-310">The WCF trace viewer understands the schema of the `TraceRecord` element shown previously and extracts the data from its child elements and displays it in a tabular format.</span></span> <span data-ttu-id="4d291-311">在跟踪结构化应用程序数据以帮助 Svctraceviewer.exe 用户读取数据时，通道应使用此架构。</span><span class="sxs-lookup"><span data-stu-id="4d291-311">Your channel should use this schema when tracing structured application data to help Svctraceviewer.exe users read the data.</span></span>
