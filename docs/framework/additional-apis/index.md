---
title: 其他类库和 API
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 049268c29946e95ca7bb194f6cae38baf8f060f6
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2018
ms.locfileid: "44361938"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="84e20-102">其他类库和 API</span><span class="sxs-lookup"><span data-stu-id="84e20-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="84e20-103">.NET Framework 在不断发展。</span><span class="sxs-lookup"><span data-stu-id="84e20-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="84e20-104">若要改善跨平台开发，并尽早引入新功能，带外 (OOB) 发布新功能。</span><span class="sxs-lookup"><span data-stu-id="84e20-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="84e20-105">本主题列出了我们提供了有关文档的 OOB 项目。</span><span class="sxs-lookup"><span data-stu-id="84e20-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="84e20-106">此外，一些库面向 .NET Framework 的特定平台或实现。</span><span class="sxs-lookup"><span data-stu-id="84e20-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="84e20-107">例如，<xref:System.Text.CodePagesEncodingProvider>类使代码页编码可用于使用.NET Framework 开发的 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="84e20-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="84e20-108">本主题还列出了以下库。</span><span class="sxs-lookup"><span data-stu-id="84e20-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="84e20-109">OOB 项目</span><span class="sxs-lookup"><span data-stu-id="84e20-109">OOB projects</span></span>
  
| <span data-ttu-id="84e20-110">项目</span><span class="sxs-lookup"><span data-stu-id="84e20-110">Project</span></span> | <span data-ttu-id="84e20-111">描述</span><span class="sxs-lookup"><span data-stu-id="84e20-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="84e20-112">提供的集合数是线程安全的，并且保证决不会更改该集合的内容。</span><span class="sxs-lookup"><span data-stu-id="84e20-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="84e20-113">基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。</span><span class="sxs-lookup"><span data-stu-id="84e20-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="84e20-114">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="84e20-114">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="84e20-115">提供可利用基于 SIMD 硬件的加速的向量类型库。</span><span class="sxs-lookup"><span data-stu-id="84e20-115">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="84e20-116">TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。</span><span class="sxs-lookup"><span data-stu-id="84e20-116">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="84e20-117">特定于平台的库</span><span class="sxs-lookup"><span data-stu-id="84e20-117">Platform-specific libraries</span></span>
  
| <span data-ttu-id="84e20-118">项目</span><span class="sxs-lookup"><span data-stu-id="84e20-118">Project</span></span> | <span data-ttu-id="84e20-119">描述</span><span class="sxs-lookup"><span data-stu-id="84e20-119">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="84e20-120">扩展了<xref:System.Text.EncodingProvider>类，以使代码页编码可用于面向通用 Windows 平台的应用。</span><span class="sxs-lookup"><span data-stu-id="84e20-120">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="84e20-121">私有 API</span><span class="sxs-lookup"><span data-stu-id="84e20-121">Private APIs</span></span>  

<span data-ttu-id="84e20-122">这些 API 支持产品基础结构，不应/不支持在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="84e20-122">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="84e20-123">API 名称</span><span class="sxs-lookup"><span data-stu-id="84e20-123">API Name</span></span> |
| -------- |
| [<span data-ttu-id="84e20-124">System.Net.Connection 类</span><span class="sxs-lookup"><span data-stu-id="84e20-124">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="84e20-125">System.Net.Connection.m\_WriteList 字段</span><span class="sxs-lookup"><span data-stu-id="84e20-125">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="84e20-126">System.Net.ConnectionGroup 类</span><span class="sxs-lookup"><span data-stu-id="84e20-126">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="84e20-127">System.Net.ConnectionGroup.m\_ConnectionList 字段</span><span class="sxs-lookup"><span data-stu-id="84e20-127">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="84e20-128">System.Net.CoreResponseData 类</span><span class="sxs-lookup"><span data-stu-id="84e20-128">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="84e20-129">System.Net.CoreResponseData.m\_ResponseHeaders 字段</span><span class="sxs-lookup"><span data-stu-id="84e20-129">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="84e20-130">System.Net.CoreResponseData.m\_StatusCode 字段</span><span class="sxs-lookup"><span data-stu-id="84e20-130">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="84e20-131">System.Net.HttpWebRequest。\_AutoRedirects 字段</span><span class="sxs-lookup"><span data-stu-id="84e20-131">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="84e20-132">System.Net.HttpWebRequest。\_CoreResponse 字段</span><span class="sxs-lookup"><span data-stu-id="84e20-132">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="84e20-133">System.Net.HttpWebRequest。\_HttpResponse 字段</span><span class="sxs-lookup"><span data-stu-id="84e20-133">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="84e20-134">System.Net.ServicePoint.m\_ConnectionGroupList 字段</span><span class="sxs-lookup"><span data-stu-id="84e20-134">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="84e20-135">System.Net.ServicePointManager.s\_ServicePointTable 字段</span><span class="sxs-lookup"><span data-stu-id="84e20-135">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="84e20-136">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes 字段</span><span class="sxs-lookup"><span data-stu-id="84e20-136">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="84e20-137">System.Windows.Forms.Design.DataMemberFieldEditor 类</span><span class="sxs-lookup"><span data-stu-id="84e20-137">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="84e20-138">System.Windows.Forms.Design.DataMemberListEditor 类</span><span class="sxs-lookup"><span data-stu-id="84e20-138">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="84e20-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="84e20-139">See also</span></span>

[<span data-ttu-id="84e20-140">.NET Framework 和带外版本</span><span class="sxs-lookup"><span data-stu-id="84e20-140">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
