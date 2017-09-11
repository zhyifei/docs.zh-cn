---
title: "其他类库和 API |Microsoft Docs"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
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
ms.translationtype: Human Translation
ms.sourcegitcommit: b53b8acc2a6c56db6a9d8a9b7c685a2d400a53e1
ms.openlocfilehash: 34815268b707aa70d174a1bbc04c32276db8412d
ms.contentlocale: zh-cn
ms.lasthandoff: 05/02/2017

---

# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="ab463-102">其他类库和 API</span><span class="sxs-lookup"><span data-stu-id="ab463-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="ab463-103">.NET Framework 不断发展，为了改善跨平台开发或尽早为客户引入新功能，我们还会发布带外 (OOB) 这一新功能。</span><span class="sxs-lookup"><span data-stu-id="ab463-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="ab463-104">本主题列出了我们提供了有关文档的 OOB 项目。</span><span class="sxs-lookup"><span data-stu-id="ab463-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="ab463-105">此外，一些库面向 .NET Framework 的特定平台或实现。</span><span class="sxs-lookup"><span data-stu-id="ab463-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="ab463-106">例如，<xref:System.Text.CodePagesEncodingProvider> 类使代码页编码可用于使用 .NET Framework 开发的 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="ab463-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="ab463-107">本主题还列出了以下库。</span><span class="sxs-lookup"><span data-stu-id="ab463-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="ab463-108">OOB 项目</span><span class="sxs-lookup"><span data-stu-id="ab463-108">OOB projects</span></span>
  
| <span data-ttu-id="ab463-109">Project</span><span class="sxs-lookup"><span data-stu-id="ab463-109">Project</span></span> | <span data-ttu-id="ab463-110">说明</span><span class="sxs-lookup"><span data-stu-id="ab463-110">Description</span></span> |  
| ------- | ----------- |  
| <span data-ttu-id="ab463-111"><xref:System.Collections.Immutable></span><span class="sxs-lookup"><span data-stu-id="ab463-111"><xref:System.Collections.Immutable></span></span> | <span data-ttu-id="ab463-112">提供的集合数是线程安全的，并且保证决不会更改该集合的内容。</span><span class="sxs-lookup"><span data-stu-id="ab463-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <span data-ttu-id="ab463-113"><xref:System.Net.Http.WinHttpHandler></span><span class="sxs-lookup"><span data-stu-id="ab463-113"><xref:System.Net.Http.WinHttpHandler></span></span> | <span data-ttu-id="ab463-114">基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。</span><span class="sxs-lookup"><span data-stu-id="ab463-114">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="ab463-115">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="ab463-115">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="ab463-116">提供可利用基于 SIMD 硬件的加速的向量类型库。</span><span class="sxs-lookup"><span data-stu-id="ab463-116">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <span data-ttu-id="ab463-117"><xref:System.Threading.Tasks.Dataflow></span><span class="sxs-lookup"><span data-stu-id="ab463-117"><xref:System.Threading.Tasks.Dataflow></span></span> | <span data-ttu-id="ab463-118">TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。</span><span class="sxs-lookup"><span data-stu-id="ab463-118">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="ab463-119">特定于平台的库</span><span class="sxs-lookup"><span data-stu-id="ab463-119">Platform-specific libraries</span></span>
  
| <span data-ttu-id="ab463-120">Project</span><span class="sxs-lookup"><span data-stu-id="ab463-120">Project</span></span> | <span data-ttu-id="ab463-121">描述</span><span class="sxs-lookup"><span data-stu-id="ab463-121">Description</span></span> |  
| ------- | ----------- |  
| <span data-ttu-id="ab463-122"><xref:System.Text.CodePagesEncodingProvider></span><span class="sxs-lookup"><span data-stu-id="ab463-122"><xref:System.Text.CodePagesEncodingProvider></span></span> | <span data-ttu-id="ab463-123">扩展 <xref:System.Text.EncodingProvider> 类，使代码页编码可用于面向通用 Windows 平台的应用。</span><span class="sxs-lookup"><span data-stu-id="ab463-123">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="ab463-124">私有 API</span><span class="sxs-lookup"><span data-stu-id="ab463-124">Private APIs</span></span>  

<span data-ttu-id="ab463-125">这些 API 支持产品基础结构，不应/不支持在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="ab463-125">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="ab463-126">API 名称</span><span class="sxs-lookup"><span data-stu-id="ab463-126">API Name</span></span> |  
| -------- |  
| [<span data-ttu-id="ab463-127">s_isDebuggerCheckDisabledForTestPurposes 字段</span><span class="sxs-lookup"><span data-stu-id="ab463-127">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |  
| [<span data-ttu-id="ab463-128">DataMemberFieldEditor 类</span><span class="sxs-lookup"><span data-stu-id="ab463-128">DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |  
| [<span data-ttu-id="ab463-129">DataMemberListEditor 类</span><span class="sxs-lookup"><span data-stu-id="ab463-129">DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |  
  
## <a name="see-also"></a><span data-ttu-id="ab463-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab463-130">See also</span></span>

[<span data-ttu-id="ab463-131">.NET Framework 和带外版本</span><span class="sxs-lookup"><span data-stu-id="ab463-131">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)

