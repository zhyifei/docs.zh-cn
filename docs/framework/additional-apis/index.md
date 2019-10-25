---
title: 其他类库和 API
ms.date: 10/17/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: 4b47847e9d6e9424d4442d655c40a637383c7229
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847084"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="a8d2b-102">其他类库和 API</span><span class="sxs-lookup"><span data-stu-id="a8d2b-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="a8d2b-103">.NET Framework 不断发展。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="a8d2b-104">若要改善跨平台开发并及早引入新功能，可通过带外（OOB）发布新功能。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="a8d2b-105">本主题列出了我们提供了有关文档的 OOB 项目。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="a8d2b-106">此外，一些库面向 .NET Framework 的特定平台或实现。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="a8d2b-107">例如，<xref:System.Text.CodePagesEncodingProvider> 类使代码页编码可用于使用 .NET Framework 开发的 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="a8d2b-108">本主题还列出了以下库。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="a8d2b-109">OOB 项目</span><span class="sxs-lookup"><span data-stu-id="a8d2b-109">OOB projects</span></span>
  
| <span data-ttu-id="a8d2b-110">项目</span><span class="sxs-lookup"><span data-stu-id="a8d2b-110">Project</span></span> | <span data-ttu-id="a8d2b-111">描述</span><span class="sxs-lookup"><span data-stu-id="a8d2b-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="a8d2b-112">提供的集合数是线程安全的，并且保证决不会更改该集合的内容。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="a8d2b-113">基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="a8d2b-114">提供可利用基于 SIMD 硬件的加速的向量类型库。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="a8d2b-115">TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="a8d2b-116">特定于平台的库</span><span class="sxs-lookup"><span data-stu-id="a8d2b-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="a8d2b-117">项目</span><span class="sxs-lookup"><span data-stu-id="a8d2b-117">Project</span></span> | <span data-ttu-id="a8d2b-118">描述</span><span class="sxs-lookup"><span data-stu-id="a8d2b-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="a8d2b-119">扩展 <xref:System.Text.EncodingProvider> 类，使代码页编码可用于面向通用 Windows 平台的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="a8d2b-120">私有 API</span><span class="sxs-lookup"><span data-stu-id="a8d2b-120">Private APIs</span></span>  

<span data-ttu-id="a8d2b-121">这些 API 支持产品基础结构，不应/不支持在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="a8d2b-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="a8d2b-122">SmiOrderProperty 属性（& e）</span><span class="sxs-lookup"><span data-stu-id="a8d2b-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="a8d2b-123">PrepForRemoting 方法</span><span class="sxs-lookup"><span data-stu-id="a8d2b-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="a8d2b-124">SqlTypes. SqlChars 属性</span><span class="sxs-lookup"><span data-stu-id="a8d2b-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="a8d2b-125">SqlTypes. SqlStreamChars 构造函数</span><span class="sxs-lookup"><span data-stu-id="a8d2b-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="a8d2b-126">SqlTypes. SqlStreamChars. CanSeek 属性</span><span class="sxs-lookup"><span data-stu-id="a8d2b-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="a8d2b-127">SqlTypes. SqlStreamChars 属性</span><span class="sxs-lookup"><span data-stu-id="a8d2b-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="a8d2b-128">SqlTypes. SqlStreamChars 属性</span><span class="sxs-lookup"><span data-stu-id="a8d2b-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="a8d2b-129">SqlTypes. SqlStreamChars 方法</span><span class="sxs-lookup"><span data-stu-id="a8d2b-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="a8d2b-130">SqlTypes. SqlStreamChars 方法</span><span class="sxs-lookup"><span data-stu-id="a8d2b-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="a8d2b-131">SqlTypes. SqlStreamChars 方法</span><span class="sxs-lookup"><span data-stu-id="a8d2b-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="a8d2b-132">SqlTypes. SqlStreamChars 方法</span><span class="sxs-lookup"><span data-stu-id="a8d2b-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="a8d2b-133">SqlTypes. SqlStreamChars 方法</span><span class="sxs-lookup"><span data-stu-id="a8d2b-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="a8d2b-134">SqlTypes. SqlStreamChars. SetLength 方法</span><span class="sxs-lookup"><span data-stu-id="a8d2b-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="a8d2b-135">SqlTypes. SqlStreamChars 方法</span><span class="sxs-lookup"><span data-stu-id="a8d2b-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="a8d2b-136">系统 .Net. 连接类</span><span class="sxs-lookup"><span data-stu-id="a8d2b-136">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="a8d2b-137">系统\_WriteList 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-137">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="a8d2b-138">ConnectionGroup 类</span><span class="sxs-lookup"><span data-stu-id="a8d2b-138">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="a8d2b-139">ConnectionGroup\_ConnectionList 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-139">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="a8d2b-140">系统 ConnectStream 属性</span><span class="sxs-lookup"><span data-stu-id="a8d2b-140">System.Net.ConnectStream.Connection Property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="a8d2b-141">CoreResponseData 类</span><span class="sxs-lookup"><span data-stu-id="a8d2b-141">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="a8d2b-142">CoreResponseData\_ResponseHeaders 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-142">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="a8d2b-143">系统 CoreResponseData\_StatusCode 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-143">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="a8d2b-144">HttpWebRequest.\_AutoRedirects 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-144">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="a8d2b-145">HttpWebRequest.\_CoreResponse 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-145">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="a8d2b-146">HttpWebRequest.\_Httpresponse.cache 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-146">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="a8d2b-147">PooledStream. NetworkStream 属性</span><span class="sxs-lookup"><span data-stu-id="a8d2b-147">System.Net.PooledStream.NetworkStream Property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="a8d2b-148">ServicePoint\_ConnectionGroupList 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-148">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="a8d2b-149">ServicePointManager\_ServicePointTable 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-149">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="a8d2b-150">TlsStream. m_Worker 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-150">System.Net.TlsStream.m_Worker Field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="a8d2b-151">SslState. SslProtocol 属性</span><span class="sxs-lookup"><span data-stu-id="a8d2b-151">System.Net.Security.SslState.SslProtocol Property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="a8d2b-152">VisualDiagnostics\_"isDebuggerCheckDisabledForTestPurposes" 字段</span><span class="sxs-lookup"><span data-stu-id="a8d2b-152">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="a8d2b-153">"DataMemberFieldEditor" 类</span><span class="sxs-lookup"><span data-stu-id="a8d2b-153">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="a8d2b-154">"DataMemberListEditor" 类</span><span class="sxs-lookup"><span data-stu-id="a8d2b-154">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="a8d2b-155">System.web. CreateSqlReader 方法</span><span class="sxs-lookup"><span data-stu-id="a8d2b-155">System.Xml.XmlReader.CreateSqlReader Method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="a8d2b-156">adodb.recordset.连接接口</span><span class="sxs-lookup"><span data-stu-id="a8d2b-156">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="a8d2b-157">adodb.recordset.EventReason 枚举</span><span class="sxs-lookup"><span data-stu-id="a8d2b-157">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="a8d2b-158">adodb.recordset.EventStatus 枚举</span><span class="sxs-lookup"><span data-stu-id="a8d2b-158">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="a8d2b-159">stdole.DISPPARAMS 结构</span><span class="sxs-lookup"><span data-stu-id="a8d2b-159">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="a8d2b-160">stdole.EXCEPINFO 结构</span><span class="sxs-lookup"><span data-stu-id="a8d2b-160">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="a8d2b-161">stdole.IFont.Name 属性</span><span class="sxs-lookup"><span data-stu-id="a8d2b-161">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="a8d2b-162">stdole.IFontDisp 接口</span><span class="sxs-lookup"><span data-stu-id="a8d2b-162">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="a8d2b-163">stdole.IPicture 属性</span><span class="sxs-lookup"><span data-stu-id="a8d2b-163">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="a8d2b-164">stdole.IPictureDisp 属性</span><span class="sxs-lookup"><span data-stu-id="a8d2b-164">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="a8d2b-165">stdole.StdFont 接口</span><span class="sxs-lookup"><span data-stu-id="a8d2b-165">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="a8d2b-166">stdole.StdPicture 接口</span><span class="sxs-lookup"><span data-stu-id="a8d2b-166">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="a8d2b-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8d2b-167">See also</span></span>

* [<span data-ttu-id="a8d2b-168">.NET Framework 和带外版本</span><span class="sxs-lookup"><span data-stu-id="a8d2b-168">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
