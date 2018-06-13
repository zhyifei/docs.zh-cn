---
title: 分析（非托管 API 参考）
ms.date: 03/30/2017
helpviewer_keywords:
- profiling [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], profiling
- unmanaged API reference [.NET Framework], profiling
ms.assetid: 14c68e84-657e-49c2-aa8b-4978dbaf4454
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 581f42dc83622712dbb30ef556a481388bafe259
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455567"
---
# <a name="profiling-unmanaged-api-reference"></a><span data-ttu-id="82f93-102">分析（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="82f93-102">Profiling (Unmanaged API Reference)</span></span>
<span data-ttu-id="82f93-103">分析 API 允许探查器公共语言运行时 (CLR) 监视程序的执行。</span><span class="sxs-lookup"><span data-stu-id="82f93-103">The profiling API enables a profiler to monitor a program's execution by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82f93-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="82f93-104">In This Section</span></span>  
 [<span data-ttu-id="82f93-105">分析概述</span><span class="sxs-lookup"><span data-stu-id="82f93-105">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
 <span data-ttu-id="82f93-106">描述的服务和 CLR 提供以在.NET Framework 环境中支持性能分析的接口。</span><span class="sxs-lookup"><span data-stu-id="82f93-106">Describes the services and interfaces that the CLR provides to support profiling in the .NET Framework environment.</span></span>  
  
 [<span data-ttu-id="82f93-107">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="82f93-107">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 <span data-ttu-id="82f93-108">描述分析 API 使用的非托管接口。</span><span class="sxs-lookup"><span data-stu-id="82f93-108">Describes the unmanaged interfaces that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="82f93-109">设置分析环境</span><span class="sxs-lookup"><span data-stu-id="82f93-109">Setting Up a Profiling Environment</span></span>](../../../../docs/framework/unmanaged-api/profiling/setting-up-a-profiling-environment.md)  
 <span data-ttu-id="82f93-110">描述.NET Framework 应用程序配置文件时必须执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="82f93-110">Describes the steps you must take to profile a .NET Framework application.</span></span>  
  
 [<span data-ttu-id="82f93-111">CLR 探查器和 Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="82f93-111">CLR Profilers and Windows Store Apps</span></span>](../../../../docs/framework/unmanaged-api/profiling/clr-profilers-and-windows-store-apps.md)  
 <span data-ttu-id="82f93-112">讨论如何端口使用 CLR 分析 API，要成功使用 Windows 应用商店应用的诊断工具。</span><span class="sxs-lookup"><span data-stu-id="82f93-112">Discusses how to port diagnostic tools that consume the CLR Profiling API to work successfully with Windows Store apps.</span></span>  
  
 [<span data-ttu-id="82f93-113">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span><span class="sxs-lookup"><span data-stu-id="82f93-113">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span></span>](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)  
 <span data-ttu-id="82f93-114">记录在其下的方法调用返回的条件`CORPROF_E_UNSUPPORTED_CALL_SEQUENCE`HRESULT。</span><span class="sxs-lookup"><span data-stu-id="82f93-114">Documents the conditions under which a method call returns the `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT.</span></span>  
  
 [<span data-ttu-id="82f93-115">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="82f93-115">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
 <span data-ttu-id="82f93-116">描述分析 API 使用的非托管全局静态函数。</span><span class="sxs-lookup"><span data-stu-id="82f93-116">Describes the unmanaged global static functions that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="82f93-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="82f93-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 <span data-ttu-id="82f93-118">描述分析 API 使用的非托管枚举。</span><span class="sxs-lookup"><span data-stu-id="82f93-118">Describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="82f93-119">分析结构</span><span class="sxs-lookup"><span data-stu-id="82f93-119">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 <span data-ttu-id="82f93-120">描述分析 API 使用的非托管结构。</span><span class="sxs-lookup"><span data-stu-id="82f93-120">Describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="82f93-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="82f93-121">Related Sections</span></span>  
 [<span data-ttu-id="82f93-122">演练：确定性能问题</span><span class="sxs-lookup"><span data-stu-id="82f93-122">Walkthrough: Identifying Performance Problems</span></span>](/visualstudio/profiling/walkthrough-identifying-performance-problems)  
 <span data-ttu-id="82f93-123">说明如何在 Microsoft Visual Studio 2005 Team System 中使用内置的分析工具。</span><span class="sxs-lookup"><span data-stu-id="82f93-123">Explains how to use the built-in profiling tools in the Microsoft Visual Studio 2005 Team System.</span></span> <span data-ttu-id="82f93-124">这些工具提供了一种方法来使用分析 API。</span><span class="sxs-lookup"><span data-stu-id="82f93-124">These tools provide an alternative approach to using the profiling API.</span></span>
