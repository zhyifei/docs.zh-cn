---
title: 其他类库和 API
ms.custom: ''
ms.date: 01/29/2018
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9ceb1ad24d4ba87fab7713ba61fed91eef26c4d
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="49d94-102">其他类库和 API</span><span class="sxs-lookup"><span data-stu-id="49d94-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="49d94-103">.NET Framework 不断发展，为了改善跨平台开发或尽早为客户引入新功能，我们还会发布带外 (OOB) 这一新功能。</span><span class="sxs-lookup"><span data-stu-id="49d94-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="49d94-104">本主题列出了我们提供了有关文档的 OOB 项目。</span><span class="sxs-lookup"><span data-stu-id="49d94-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="49d94-105">此外，一些库面向 .NET Framework 的特定平台或实现。</span><span class="sxs-lookup"><span data-stu-id="49d94-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="49d94-106">例如，<xref:System.Text.CodePagesEncodingProvider>类，使代码页编码可用于 UWP 应用使用.NET Framework 开发。</span><span class="sxs-lookup"><span data-stu-id="49d94-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="49d94-107">本主题还列出了以下库。</span><span class="sxs-lookup"><span data-stu-id="49d94-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="49d94-108">OOB 项目</span><span class="sxs-lookup"><span data-stu-id="49d94-108">OOB projects</span></span>
  
| <span data-ttu-id="49d94-109">项目</span><span class="sxs-lookup"><span data-stu-id="49d94-109">Project</span></span> | <span data-ttu-id="49d94-110">描述</span><span class="sxs-lookup"><span data-stu-id="49d94-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="49d94-111">提供的集合数是线程安全的，并且保证决不会更改该集合的内容。</span><span class="sxs-lookup"><span data-stu-id="49d94-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="49d94-112">基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。</span><span class="sxs-lookup"><span data-stu-id="49d94-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="49d94-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="49d94-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="49d94-114">提供可利用基于 SIMD 硬件的加速的向量类型库。</span><span class="sxs-lookup"><span data-stu-id="49d94-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="49d94-115">TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。</span><span class="sxs-lookup"><span data-stu-id="49d94-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="49d94-116">特定于平台的库</span><span class="sxs-lookup"><span data-stu-id="49d94-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="49d94-117">项目</span><span class="sxs-lookup"><span data-stu-id="49d94-117">Project</span></span> | <span data-ttu-id="49d94-118">描述</span><span class="sxs-lookup"><span data-stu-id="49d94-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="49d94-119">扩展<xref:System.Text.EncodingProvider>要提供给面向通用 Windows 平台的应用代码页编码的类。</span><span class="sxs-lookup"><span data-stu-id="49d94-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="49d94-120">私有 API</span><span class="sxs-lookup"><span data-stu-id="49d94-120">Private APIs</span></span>  

<span data-ttu-id="49d94-121">这些 API 支持产品基础结构，不应/不支持在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="49d94-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="49d94-122">API 名称</span><span class="sxs-lookup"><span data-stu-id="49d94-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="49d94-123">System.Net.Connection 类</span><span class="sxs-lookup"><span data-stu-id="49d94-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="49d94-124">System.Net.Connection.m\_WriteList 字段</span><span class="sxs-lookup"><span data-stu-id="49d94-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="49d94-125">System.Net.ConnectionGroup 类</span><span class="sxs-lookup"><span data-stu-id="49d94-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="49d94-126">System.Net.ConnectionGroup.m\_ConnectionList 字段</span><span class="sxs-lookup"><span data-stu-id="49d94-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="49d94-127">System.Net.CoreResponseData 类</span><span class="sxs-lookup"><span data-stu-id="49d94-127">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="49d94-128">System.Net.CoreResponseData.m\_ResponseHeaders 字段</span><span class="sxs-lookup"><span data-stu-id="49d94-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="49d94-129">System.Net.CoreResponseData.m\_StatusCode 字段</span><span class="sxs-lookup"><span data-stu-id="49d94-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="49d94-130">System.Net.HttpWebRequest。\_AutoRedirects 字段</span><span class="sxs-lookup"><span data-stu-id="49d94-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="49d94-131">System.Net.HttpWebRequest。\_CoreResponse 字段</span><span class="sxs-lookup"><span data-stu-id="49d94-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="49d94-132">System.Net.HttpWebRequest。\_HttpResponse 字段</span><span class="sxs-lookup"><span data-stu-id="49d94-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="49d94-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span><span class="sxs-lookup"><span data-stu-id="49d94-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="49d94-134">System.Net.ServicePointManager.s\_ServicePointTable 字段</span><span class="sxs-lookup"><span data-stu-id="49d94-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="49d94-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="49d94-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="49d94-136">System.Windows.Forms.Design.DataMemberFieldEditor 类</span><span class="sxs-lookup"><span data-stu-id="49d94-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="49d94-137">System.Windows.Forms.Design.DataMemberListEditor 类</span><span class="sxs-lookup"><span data-stu-id="49d94-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="49d94-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="49d94-138">See also</span></span>

[<span data-ttu-id="49d94-139">.NET Framework 和带外版本</span><span class="sxs-lookup"><span data-stu-id="49d94-139">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
