---
title: 其他类库和 API
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: abf7fd20988ebaaaf1a40ccc168c636fd0dacc1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155903"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="f8acf-102">其他类库和 API</span><span class="sxs-lookup"><span data-stu-id="f8acf-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="f8acf-103">.NET 框架在不断发展。</span><span class="sxs-lookup"><span data-stu-id="f8acf-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="f8acf-104">为了改进跨平台开发并尽早引入新功能，新功能将发布在频段 （OOB） 外。</span><span class="sxs-lookup"><span data-stu-id="f8acf-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="f8acf-105">本主题列出了我们提供了有关文档的 OOB 项目。</span><span class="sxs-lookup"><span data-stu-id="f8acf-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="f8acf-106">此外，一些库面向 .NET Framework 的特定平台或实现。</span><span class="sxs-lookup"><span data-stu-id="f8acf-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="f8acf-107">例如，<xref:System.Text.CodePagesEncodingProvider>类使代码页编码可用于使用 .NET 框架开发的 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="f8acf-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="f8acf-108">本主题还列出了以下库。</span><span class="sxs-lookup"><span data-stu-id="f8acf-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="f8acf-109">OOB 项目</span><span class="sxs-lookup"><span data-stu-id="f8acf-109">OOB projects</span></span>
  
| <span data-ttu-id="f8acf-110">Project</span><span class="sxs-lookup"><span data-stu-id="f8acf-110">Project</span></span> | <span data-ttu-id="f8acf-111">说明</span><span class="sxs-lookup"><span data-stu-id="f8acf-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="f8acf-112">提供的集合数是线程安全的，并且保证决不会更改该集合的内容。</span><span class="sxs-lookup"><span data-stu-id="f8acf-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="f8acf-113">基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。</span><span class="sxs-lookup"><span data-stu-id="f8acf-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="f8acf-114">提供可利用基于 SIMD 硬件的加速的向量类型库。</span><span class="sxs-lookup"><span data-stu-id="f8acf-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="f8acf-115">TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。</span><span class="sxs-lookup"><span data-stu-id="f8acf-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="f8acf-116">特定于平台的库</span><span class="sxs-lookup"><span data-stu-id="f8acf-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="f8acf-117">Project</span><span class="sxs-lookup"><span data-stu-id="f8acf-117">Project</span></span> | <span data-ttu-id="f8acf-118">说明</span><span class="sxs-lookup"><span data-stu-id="f8acf-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="f8acf-119">扩展类<xref:System.Text.EncodingProvider>，使代码页编码可用于面向通用 Windows 平台的应用。</span><span class="sxs-lookup"><span data-stu-id="f8acf-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="f8acf-120">私有 API</span><span class="sxs-lookup"><span data-stu-id="f8acf-120">Private APIs</span></span>  

<span data-ttu-id="f8acf-121">这些 API 支持产品基础结构，不应/不支持在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="f8acf-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="f8acf-122">微软.SqlServer.Server.Smiorder属性.项目属性</span><span class="sxs-lookup"><span data-stu-id="f8acf-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="f8acf-123">系统.例外.准备重新移动方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="f8acf-124">系统.数据.SqlTypes.SqlChars.流属性</span><span class="sxs-lookup"><span data-stu-id="f8acf-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="f8acf-125">系统.数据.SqlTypes.SqlStreamChars构造函数</span><span class="sxs-lookup"><span data-stu-id="f8acf-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="f8acf-126">系统.数据.SqlTypes.SqlStreamChars.CanSeek 属性</span><span class="sxs-lookup"><span data-stu-id="f8acf-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="f8acf-127">系统.数据.SqlTypes.SqlStreamChars.IsNull 属性</span><span class="sxs-lookup"><span data-stu-id="f8acf-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="f8acf-128">系统.数据.SqlTypes.SqlStreamChars.长度属性</span><span class="sxs-lookup"><span data-stu-id="f8acf-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="f8acf-129">系统.数据.SqlTypes.SqlStreamChars.关闭方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="f8acf-130">系统.数据.SqlTypes.SqlStreamChars.Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="f8acf-131">系统.数据.SqlTypes.SqlStreamChars.Flush 方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="f8acf-132">系统.数据.SqlTypes.SqlStreamChars.读取方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="f8acf-133">系统.数据.SqlTypes.SqlStreamChars.查找方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="f8acf-134">系统.数据.SqlTypes.SqlStreamChars.set 长度方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="f8acf-135">系统.数据.SqlTypes.SqlStreamChars.写入方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="f8acf-136">系统.IO.内存流.内部获取源和长度方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-136">System.IO.MemoryStream.InternalGetOriginAndLength Method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="f8acf-137">系统.Net.连接类</span><span class="sxs-lookup"><span data-stu-id="f8acf-137">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="f8acf-138">系统.Net.连接.m\_写入列表字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-138">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="f8acf-139">系统.Net.连接组类</span><span class="sxs-lookup"><span data-stu-id="f8acf-139">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="f8acf-140">系统.Net.连接组.m\_连接列表字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-140">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="f8acf-141">系统.Net.连接流.连接属性</span><span class="sxs-lookup"><span data-stu-id="f8acf-141">System.Net.ConnectStream.Connection Property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="f8acf-142">系统.Net.核心响应数据类</span><span class="sxs-lookup"><span data-stu-id="f8acf-142">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="f8acf-143">系统.Net.核心响应数据.m\_响应标题字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-143">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="f8acf-144">系统.Net.核心响应数据.m\_状态代码字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-144">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="f8acf-145">系统.Net.HttpWeb请求。\_自动重定向字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-145">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="f8acf-146">系统.Net.HttpWeb请求。\_核心响应字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-146">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="f8acf-147">系统.Net.HttpWeb请求。\_Http 响应字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-147">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="f8acf-148">系统.Net.池流.网络流属性</span><span class="sxs-lookup"><span data-stu-id="f8acf-148">System.Net.PooledStream.NetworkStream Property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="f8acf-149">系统.Net.RtcState 类</span><span class="sxs-lookup"><span data-stu-id="f8acf-149">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="f8acf-150">系统.Net.服务点.m\_连接组列表字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-150">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="f8acf-151">系统.Net.服务点管理器.的服务\_点表字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-151">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="f8acf-152">系统.Net.TlsStream.m_Worker字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-152">System.Net.TlsStream.m_Worker Field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="f8acf-153">系统.Net.Security.SslState.Ssl协议属性</span><span class="sxs-lookup"><span data-stu-id="f8acf-153">System.Net.Security.SslState.SslProtocol Property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="f8acf-154">系统.服务模式.通道.消息.正文string方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-154">System.ServiceModel.Channels.Message.BodyToString Method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="f8acf-155">系统.服务模式.通道.消息.编写开始标题方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-155">System.ServiceModel.Channels.Message.WriteStartHeaders Method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="f8acf-156">系统.Windows.诊断.视觉诊断是\_调试器检查禁用的"测试目的"字段</span><span class="sxs-lookup"><span data-stu-id="f8acf-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="f8acf-157">系统.Windows.窗体.设计.数据成员字段编辑器类</span><span class="sxs-lookup"><span data-stu-id="f8acf-157">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="f8acf-158">系统.Windows.窗体.设计.数据成员列表编辑器类</span><span class="sxs-lookup"><span data-stu-id="f8acf-158">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="f8acf-159">系统.Xml.XmlReader.createSqlReader方法</span><span class="sxs-lookup"><span data-stu-id="f8acf-159">System.Xml.XmlReader.CreateSqlReader Method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="f8acf-160">阿多德布连接接口</span><span class="sxs-lookup"><span data-stu-id="f8acf-160">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="f8acf-161">阿多德布事件原因枚举</span><span class="sxs-lookup"><span data-stu-id="f8acf-161">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="f8acf-162">阿多德布事件状态枚举</span><span class="sxs-lookup"><span data-stu-id="f8acf-162">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="f8acf-163">stdole。DISPPARAMS 结构</span><span class="sxs-lookup"><span data-stu-id="f8acf-163">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="f8acf-164">stdole。EXCEPINFO 结构</span><span class="sxs-lookup"><span data-stu-id="f8acf-164">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="f8acf-165">stdole。IFont.Name酒店</span><span class="sxs-lookup"><span data-stu-id="f8acf-165">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="f8acf-166">stdole。IFontDisp 接口</span><span class="sxs-lookup"><span data-stu-id="f8acf-166">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="f8acf-167">stdole。IPicture.Handle 属性</span><span class="sxs-lookup"><span data-stu-id="f8acf-167">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="f8acf-168">stdole。IPictureDisp.Handle 属性</span><span class="sxs-lookup"><span data-stu-id="f8acf-168">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="f8acf-169">stdole。斯特芬接口</span><span class="sxs-lookup"><span data-stu-id="f8acf-169">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="f8acf-170">stdole。StdPicture 界面</span><span class="sxs-lookup"><span data-stu-id="f8acf-170">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="f8acf-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8acf-171">See also</span></span>

* [<span data-ttu-id="f8acf-172">.NET Framework 和带外版本</span><span class="sxs-lookup"><span data-stu-id="f8acf-172">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
