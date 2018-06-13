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
ms.openlocfilehash: 65925b7dafb9e89433253d68327c488365674963
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406262"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="9c206-102">常量（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="9c206-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="9c206-103">本主题介绍语言类型、 语言提供商和在 CorSym.idl 中定义的文档类型常量。</span><span class="sxs-lookup"><span data-stu-id="9c206-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="9c206-104">语言类型常量</span><span class="sxs-lookup"><span data-stu-id="9c206-104">Language Type Constants</span></span>  
 <span data-ttu-id="9c206-105">下表显示语言类型常量，表示用于识别编程语言的 Guid。</span><span class="sxs-lookup"><span data-stu-id="9c206-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="9c206-106">符号</span><span class="sxs-lookup"><span data-stu-id="9c206-106">Symbol</span></span>|<span data-ttu-id="9c206-107">描述</span><span class="sxs-lookup"><span data-stu-id="9c206-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9c206-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="9c206-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="9c206-109">指示的 C 语言。</span><span class="sxs-lookup"><span data-stu-id="9c206-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="9c206-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="9c206-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="9c206-111">指示的 c + + 语言。</span><span class="sxs-lookup"><span data-stu-id="9c206-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="9c206-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="9c206-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="9c206-113">指示的 C# 语言。</span><span class="sxs-lookup"><span data-stu-id="9c206-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="9c206-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="9c206-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="9c206-115">指示的基本语言。</span><span class="sxs-lookup"><span data-stu-id="9c206-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="9c206-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="9c206-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="9c206-117">指示 Java 语言。</span><span class="sxs-lookup"><span data-stu-id="9c206-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="9c206-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="9c206-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="9c206-119">指示 COBOL 语言。</span><span class="sxs-lookup"><span data-stu-id="9c206-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="9c206-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="9c206-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="9c206-121">指示 Pascal 语言。</span><span class="sxs-lookup"><span data-stu-id="9c206-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="9c206-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="9c206-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="9c206-123">表示 Microsoft 中间语言 (MSIL) 程序集代码。</span><span class="sxs-lookup"><span data-stu-id="9c206-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="9c206-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="9c206-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="9c206-125">指示 JScript 语言。</span><span class="sxs-lookup"><span data-stu-id="9c206-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="9c206-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="9c206-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="9c206-127">指示 SMC 语言。</span><span class="sxs-lookup"><span data-stu-id="9c206-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="9c206-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="9c206-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="9c206-129">指示启用.NET framework 的 c + + 语言。</span><span class="sxs-lookup"><span data-stu-id="9c206-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="9c206-130">语言供应商常量</span><span class="sxs-lookup"><span data-stu-id="9c206-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="9c206-131">下表显示语言供应商常量，表示用于识别编程语言提供商的 Guid。</span><span class="sxs-lookup"><span data-stu-id="9c206-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="9c206-132">符号</span><span class="sxs-lookup"><span data-stu-id="9c206-132">Symbol</span></span>|<span data-ttu-id="9c206-133">描述</span><span class="sxs-lookup"><span data-stu-id="9c206-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9c206-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="9c206-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="9c206-135">指示 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="9c206-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="9c206-136">文档类型常量</span><span class="sxs-lookup"><span data-stu-id="9c206-136">Document Type Constants</span></span>  
 <span data-ttu-id="9c206-137">下表显示文档类型常量，表示文档类型进行标识的 Guid。</span><span class="sxs-lookup"><span data-stu-id="9c206-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="9c206-138">符号</span><span class="sxs-lookup"><span data-stu-id="9c206-138">Symbol</span></span>|<span data-ttu-id="9c206-139">描述</span><span class="sxs-lookup"><span data-stu-id="9c206-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9c206-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="9c206-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="9c206-141">表示一个文本文档。</span><span class="sxs-lookup"><span data-stu-id="9c206-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="9c206-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="9c206-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="9c206-143">指示非文本文档。</span><span class="sxs-lookup"><span data-stu-id="9c206-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c206-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c206-144">See Also</span></span>  
 [<span data-ttu-id="9c206-145">非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="9c206-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
