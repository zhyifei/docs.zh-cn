---
title: "常量（非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e086e856bb7a872b14815825f78d208ff5296899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="ffe70-102">常量（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="ffe70-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="ffe70-103">本主题介绍语言类型、 语言提供商和在 CorSym.idl 中定义的文档类型常量。</span><span class="sxs-lookup"><span data-stu-id="ffe70-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="ffe70-104">语言类型常量</span><span class="sxs-lookup"><span data-stu-id="ffe70-104">Language Type Constants</span></span>  
 <span data-ttu-id="ffe70-105">下表显示语言类型常量，表示用于识别编程语言的 Guid。</span><span class="sxs-lookup"><span data-stu-id="ffe70-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="ffe70-106">符号</span><span class="sxs-lookup"><span data-stu-id="ffe70-106">Symbol</span></span>|<span data-ttu-id="ffe70-107">描述</span><span class="sxs-lookup"><span data-stu-id="ffe70-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ffe70-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="ffe70-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="ffe70-109">指示的 C 语言。</span><span class="sxs-lookup"><span data-stu-id="ffe70-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="ffe70-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="ffe70-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="ffe70-111">指示的 c + + 语言。</span><span class="sxs-lookup"><span data-stu-id="ffe70-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="ffe70-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="ffe70-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="ffe70-113">指示的 C# 语言。</span><span class="sxs-lookup"><span data-stu-id="ffe70-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="ffe70-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="ffe70-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="ffe70-115">指示的基本语言。</span><span class="sxs-lookup"><span data-stu-id="ffe70-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="ffe70-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="ffe70-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="ffe70-117">指示 Java 语言。</span><span class="sxs-lookup"><span data-stu-id="ffe70-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="ffe70-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="ffe70-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="ffe70-119">指示 COBOL 语言。</span><span class="sxs-lookup"><span data-stu-id="ffe70-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="ffe70-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="ffe70-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="ffe70-121">指示 Pascal 语言。</span><span class="sxs-lookup"><span data-stu-id="ffe70-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="ffe70-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="ffe70-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="ffe70-123">表示 Microsoft 中间语言 (MSIL) 程序集代码。</span><span class="sxs-lookup"><span data-stu-id="ffe70-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="ffe70-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="ffe70-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="ffe70-125">指示 JScript 语言。</span><span class="sxs-lookup"><span data-stu-id="ffe70-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="ffe70-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="ffe70-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="ffe70-127">指示 SMC 语言。</span><span class="sxs-lookup"><span data-stu-id="ffe70-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="ffe70-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="ffe70-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="ffe70-129">指示启用.NET framework 的 c + + 语言。</span><span class="sxs-lookup"><span data-stu-id="ffe70-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="ffe70-130">语言供应商常量</span><span class="sxs-lookup"><span data-stu-id="ffe70-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="ffe70-131">下表显示语言供应商常量，表示用于识别编程语言提供商的 Guid。</span><span class="sxs-lookup"><span data-stu-id="ffe70-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="ffe70-132">符号</span><span class="sxs-lookup"><span data-stu-id="ffe70-132">Symbol</span></span>|<span data-ttu-id="ffe70-133">描述</span><span class="sxs-lookup"><span data-stu-id="ffe70-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ffe70-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="ffe70-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="ffe70-135">指示 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="ffe70-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="ffe70-136">文档类型常量</span><span class="sxs-lookup"><span data-stu-id="ffe70-136">Document Type Constants</span></span>  
 <span data-ttu-id="ffe70-137">下表显示文档类型常量，表示文档类型进行标识的 Guid。</span><span class="sxs-lookup"><span data-stu-id="ffe70-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="ffe70-138">符号</span><span class="sxs-lookup"><span data-stu-id="ffe70-138">Symbol</span></span>|<span data-ttu-id="ffe70-139">描述</span><span class="sxs-lookup"><span data-stu-id="ffe70-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ffe70-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="ffe70-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="ffe70-141">表示一个文本文档。</span><span class="sxs-lookup"><span data-stu-id="ffe70-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="ffe70-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="ffe70-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="ffe70-143">指示非文本文档。</span><span class="sxs-lookup"><span data-stu-id="ffe70-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ffe70-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffe70-144">See Also</span></span>  
 [<span data-ttu-id="ffe70-145">非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="ffe70-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
