---
title: "其他类库和 API"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c22de3ed401e0be10b155649395da43cedb35e6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="d6d45-102">其他类库和 API</span><span class="sxs-lookup"><span data-stu-id="d6d45-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="d6d45-103">.NET Framework 不断发展，为了改善跨平台开发或尽早为客户引入新功能，我们还会发布带外 (OOB) 这一新功能。</span><span class="sxs-lookup"><span data-stu-id="d6d45-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="d6d45-104">本主题列出了我们提供了有关文档的 OOB 项目。</span><span class="sxs-lookup"><span data-stu-id="d6d45-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="d6d45-105">此外，一些库面向 .NET Framework 的特定平台或实现。</span><span class="sxs-lookup"><span data-stu-id="d6d45-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="d6d45-106">例如，<xref:System.Text.CodePagesEncodingProvider>类，使代码页编码可用于 UWP 应用使用.NET Framework 开发。</span><span class="sxs-lookup"><span data-stu-id="d6d45-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="d6d45-107">本主题还列出了以下库。</span><span class="sxs-lookup"><span data-stu-id="d6d45-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="d6d45-108">OOB 项目</span><span class="sxs-lookup"><span data-stu-id="d6d45-108">OOB projects</span></span>
  
| <span data-ttu-id="d6d45-109">项目</span><span class="sxs-lookup"><span data-stu-id="d6d45-109">Project</span></span> | <span data-ttu-id="d6d45-110">描述</span><span class="sxs-lookup"><span data-stu-id="d6d45-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="d6d45-111">提供的集合数是线程安全的，并且保证决不会更改该集合的内容。</span><span class="sxs-lookup"><span data-stu-id="d6d45-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="d6d45-112">基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。</span><span class="sxs-lookup"><span data-stu-id="d6d45-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="d6d45-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="d6d45-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="d6d45-114">提供可利用基于 SIMD 硬件的加速的向量类型库。</span><span class="sxs-lookup"><span data-stu-id="d6d45-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="d6d45-115">TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。</span><span class="sxs-lookup"><span data-stu-id="d6d45-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="d6d45-116">特定于平台的库</span><span class="sxs-lookup"><span data-stu-id="d6d45-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="d6d45-117">项目</span><span class="sxs-lookup"><span data-stu-id="d6d45-117">Project</span></span> | <span data-ttu-id="d6d45-118">描述</span><span class="sxs-lookup"><span data-stu-id="d6d45-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="d6d45-119">扩展<xref:System.Text.EncodingProvider>要提供给面向通用 Windows 平台的应用代码页编码的类。</span><span class="sxs-lookup"><span data-stu-id="d6d45-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="d6d45-120">私有 API</span><span class="sxs-lookup"><span data-stu-id="d6d45-120">Private APIs</span></span>  

<span data-ttu-id="d6d45-121">这些 API 支持产品基础结构，不应/不支持在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="d6d45-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="d6d45-122">API 名称</span><span class="sxs-lookup"><span data-stu-id="d6d45-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="d6d45-123">System.Net.Connection 类</span><span class="sxs-lookup"><span data-stu-id="d6d45-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="d6d45-124">System.Net.Connection.m\_WriteList 字段</span><span class="sxs-lookup"><span data-stu-id="d6d45-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="d6d45-125">System.Net.ConnectionGroup 类</span><span class="sxs-lookup"><span data-stu-id="d6d45-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="d6d45-126">System.Net.ConnectionGroup.m\_ConnectionList 字段</span><span class="sxs-lookup"><span data-stu-id="d6d45-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="d6d45-127">System.Net.HttpWebRequest。\_HttpResponse 字段</span><span class="sxs-lookup"><span data-stu-id="d6d45-127">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="d6d45-128">System.Net.HttpWebRequest。\_AutoRedirects 字段</span><span class="sxs-lookup"><span data-stu-id="d6d45-128">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="d6d45-129">System.Net.ServicePoint.m\_ConnectionGroupList 字段</span><span class="sxs-lookup"><span data-stu-id="d6d45-129">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="d6d45-130">System.Net.ServicePointManager.s\_ServicePointTable 字段</span><span class="sxs-lookup"><span data-stu-id="d6d45-130">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="d6d45-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes 字段</span><span class="sxs-lookup"><span data-stu-id="d6d45-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="d6d45-132">System.Windows.Forms.Design.DataMemberFieldEditor 类</span><span class="sxs-lookup"><span data-stu-id="d6d45-132">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="d6d45-133">System.Windows.Forms.Design.DataMemberListEditor 类</span><span class="sxs-lookup"><span data-stu-id="d6d45-133">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="d6d45-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6d45-134">See also</span></span>

[<span data-ttu-id="d6d45-135">.NET Framework 和带外版本</span><span class="sxs-lookup"><span data-stu-id="d6d45-135">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
