---
title: 常量（非托管 API 参考）
ms.date: 03/30/2017
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b91f2a749557f94a68f1929d649824719160d9ee
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786953"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="b25d8-102">常量（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="b25d8-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="b25d8-103">本主题介绍 CorSym 中定义的语言类型、语言供应商和文档类型常量。</span><span class="sxs-lookup"><span data-stu-id="b25d8-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="b25d8-104">语言类型常量</span><span class="sxs-lookup"><span data-stu-id="b25d8-104">Language Type Constants</span></span>  
 <span data-ttu-id="b25d8-105">下表显示了语言类型常量，它们表示标识编程语言的 Guid。</span><span class="sxs-lookup"><span data-stu-id="b25d8-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="b25d8-106">符号</span><span class="sxs-lookup"><span data-stu-id="b25d8-106">Symbol</span></span>|<span data-ttu-id="b25d8-107">描述</span><span class="sxs-lookup"><span data-stu-id="b25d8-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b25d8-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="b25d8-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="b25d8-109">指示 C 语言。</span><span class="sxs-lookup"><span data-stu-id="b25d8-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="b25d8-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="b25d8-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="b25d8-111">指示C++语言。</span><span class="sxs-lookup"><span data-stu-id="b25d8-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="b25d8-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="b25d8-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="b25d8-113">指示C#语言。</span><span class="sxs-lookup"><span data-stu-id="b25d8-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="b25d8-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="b25d8-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="b25d8-115">指示基本语言。</span><span class="sxs-lookup"><span data-stu-id="b25d8-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="b25d8-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="b25d8-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="b25d8-117">指示 Java 语言。</span><span class="sxs-lookup"><span data-stu-id="b25d8-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="b25d8-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="b25d8-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="b25d8-119">指示 COBOL 语言。</span><span class="sxs-lookup"><span data-stu-id="b25d8-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="b25d8-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="b25d8-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="b25d8-121">指示 Pascal 语言。</span><span class="sxs-lookup"><span data-stu-id="b25d8-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="b25d8-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="b25d8-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="b25d8-123">指示 Microsoft 中间语言（MSIL）程序集代码。</span><span class="sxs-lookup"><span data-stu-id="b25d8-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="b25d8-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="b25d8-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="b25d8-125">指示 JScript 语言。</span><span class="sxs-lookup"><span data-stu-id="b25d8-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="b25d8-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="b25d8-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="b25d8-127">指示 SMC 语言。</span><span class="sxs-lookup"><span data-stu-id="b25d8-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="b25d8-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="b25d8-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="b25d8-129">指示为C++ .NET Framework 启用的语言。</span><span class="sxs-lookup"><span data-stu-id="b25d8-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="b25d8-130">语言供应商常量</span><span class="sxs-lookup"><span data-stu-id="b25d8-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="b25d8-131">下表显示了语言供应商常量，它们表示标识编程语言供应商的 Guid。</span><span class="sxs-lookup"><span data-stu-id="b25d8-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="b25d8-132">符号</span><span class="sxs-lookup"><span data-stu-id="b25d8-132">Symbol</span></span>|<span data-ttu-id="b25d8-133">描述</span><span class="sxs-lookup"><span data-stu-id="b25d8-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b25d8-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="b25d8-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="b25d8-135">指示 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="b25d8-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="b25d8-136">文档类型常量</span><span class="sxs-lookup"><span data-stu-id="b25d8-136">Document Type Constants</span></span>  
 <span data-ttu-id="b25d8-137">下表显示了文档类型常量，它们表示标识文档类型的 Guid。</span><span class="sxs-lookup"><span data-stu-id="b25d8-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="b25d8-138">符号</span><span class="sxs-lookup"><span data-stu-id="b25d8-138">Symbol</span></span>|<span data-ttu-id="b25d8-139">描述</span><span class="sxs-lookup"><span data-stu-id="b25d8-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b25d8-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="b25d8-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="b25d8-141">指示文本文档。</span><span class="sxs-lookup"><span data-stu-id="b25d8-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="b25d8-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="b25d8-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="b25d8-143">指示非文本文档。</span><span class="sxs-lookup"><span data-stu-id="b25d8-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b25d8-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="b25d8-144">See also</span></span>

- [<span data-ttu-id="b25d8-145">非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="b25d8-145">Unmanaged API Reference</span></span>](index.md)
