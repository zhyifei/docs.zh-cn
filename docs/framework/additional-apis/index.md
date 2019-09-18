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
ms.topic: conceptual
ms.openlocfilehash: 0aed6f32bbd3ffdc9446e9d17be2d90c62444ee1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053240"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="61adb-102">其他类库和 API</span><span class="sxs-lookup"><span data-stu-id="61adb-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="61adb-103">.NET Framework 不断发展。</span><span class="sxs-lookup"><span data-stu-id="61adb-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="61adb-104">若要改善跨平台开发并及早引入新功能，可通过带外（OOB）发布新功能。</span><span class="sxs-lookup"><span data-stu-id="61adb-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="61adb-105">本主题列出了我们提供了有关文档的 OOB 项目。</span><span class="sxs-lookup"><span data-stu-id="61adb-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="61adb-106">此外，一些库面向 .NET Framework 的特定平台或实现。</span><span class="sxs-lookup"><span data-stu-id="61adb-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="61adb-107">例如， <xref:System.Text.CodePagesEncodingProvider>类使代码页编码可用于使用 .NET Framework 开发的 UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="61adb-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="61adb-108">本主题还列出了以下库。</span><span class="sxs-lookup"><span data-stu-id="61adb-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="61adb-109">OOB 项目</span><span class="sxs-lookup"><span data-stu-id="61adb-109">OOB projects</span></span>
  
| <span data-ttu-id="61adb-110">项目</span><span class="sxs-lookup"><span data-stu-id="61adb-110">Project</span></span> | <span data-ttu-id="61adb-111">描述</span><span class="sxs-lookup"><span data-stu-id="61adb-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="61adb-112">提供的集合数是线程安全的，并且保证决不会更改该集合的内容。</span><span class="sxs-lookup"><span data-stu-id="61adb-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="61adb-113">基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。</span><span class="sxs-lookup"><span data-stu-id="61adb-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="61adb-114">提供可利用基于 SIMD 硬件的加速的向量类型库。</span><span class="sxs-lookup"><span data-stu-id="61adb-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="61adb-115">TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。</span><span class="sxs-lookup"><span data-stu-id="61adb-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="61adb-116">特定于平台的库</span><span class="sxs-lookup"><span data-stu-id="61adb-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="61adb-117">项目</span><span class="sxs-lookup"><span data-stu-id="61adb-117">Project</span></span> | <span data-ttu-id="61adb-118">描述</span><span class="sxs-lookup"><span data-stu-id="61adb-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="61adb-119"><xref:System.Text.EncodingProvider>扩展类，使代码页编码可用于面向通用 Windows 平台的应用程序。</span><span class="sxs-lookup"><span data-stu-id="61adb-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="61adb-120">私有 API</span><span class="sxs-lookup"><span data-stu-id="61adb-120">Private APIs</span></span>  

<span data-ttu-id="61adb-121">这些 API 支持产品基础结构，不应/不支持在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="61adb-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="61adb-122">API 名称</span><span class="sxs-lookup"><span data-stu-id="61adb-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="61adb-123">系统 .Net. 连接类</span><span class="sxs-lookup"><span data-stu-id="61adb-123">System.Net.Connection Class</span></span>](connection.md) |
| [<span data-ttu-id="61adb-124">\_系统 WriteList 字段</span><span class="sxs-lookup"><span data-stu-id="61adb-124">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md) |
| [<span data-ttu-id="61adb-125">ConnectionGroup 类</span><span class="sxs-lookup"><span data-stu-id="61adb-125">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md) |
| [<span data-ttu-id="61adb-126">系统 ConnectionGroup\_ConnectionList 字段</span><span class="sxs-lookup"><span data-stu-id="61adb-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md) |
| [<span data-ttu-id="61adb-127">CoreResponseData 类</span><span class="sxs-lookup"><span data-stu-id="61adb-127">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md) |
| [<span data-ttu-id="61adb-128">系统 CoreResponseData\_ResponseHeaders 字段</span><span class="sxs-lookup"><span data-stu-id="61adb-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="61adb-129">系统 CoreResponseData\_StatusCode 字段</span><span class="sxs-lookup"><span data-stu-id="61adb-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="61adb-130">系统 HttpWebRequest。\_AutoRedirects 字段</span><span class="sxs-lookup"><span data-stu-id="61adb-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md) |
| [<span data-ttu-id="61adb-131">系统 HttpWebRequest。\_CoreResponse 字段</span><span class="sxs-lookup"><span data-stu-id="61adb-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="61adb-132">系统 HttpWebRequest。\_Httpresponse.cache 字段</span><span class="sxs-lookup"><span data-stu-id="61adb-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md) |
| [<span data-ttu-id="61adb-133">系统 ServicePoint\_ConnectionGroupList 字段</span><span class="sxs-lookup"><span data-stu-id="61adb-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md) |
| [<span data-ttu-id="61adb-134">系统 ServicePointManager\_ServicePointTable 字段</span><span class="sxs-lookup"><span data-stu-id="61adb-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md) |
| [<span data-ttu-id="61adb-135">VisualDiagnostics. s\_isDebuggerCheckDisabledForTestPurposes 字段</span><span class="sxs-lookup"><span data-stu-id="61adb-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="61adb-136">"DataMemberFieldEditor" 类</span><span class="sxs-lookup"><span data-stu-id="61adb-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md) |
| [<span data-ttu-id="61adb-137">"DataMemberListEditor" 类</span><span class="sxs-lookup"><span data-stu-id="61adb-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="61adb-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="61adb-138">See also</span></span>

- [<span data-ttu-id="61adb-139">.NET Framework 和带外版本</span><span class="sxs-lookup"><span data-stu-id="61adb-139">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
