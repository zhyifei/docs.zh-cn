---
title: '#pragma（C# 参考）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6f53bd0ed3f35f049b0a1cbb21c5b9a563f9fce9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="pragma-c-reference"></a><span data-ttu-id="3557f-102">#pragma（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3557f-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="3557f-103">`#pragma` 为编译器给出特殊指令以编译它所在的文件。</span><span class="sxs-lookup"><span data-stu-id="3557f-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="3557f-104">这些指令必须受编译器支持。</span><span class="sxs-lookup"><span data-stu-id="3557f-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="3557f-105">即是说，不可使用 `#pragma` 创建自定义处理指令。</span><span class="sxs-lookup"><span data-stu-id="3557f-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="3557f-106">Microsoft C# 编译器支持以下两种 `#pragma` 指令：</span><span class="sxs-lookup"><span data-stu-id="3557f-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="3557f-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3557f-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="3557f-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3557f-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="3557f-109">语法</span><span class="sxs-lookup"><span data-stu-id="3557f-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3557f-110">参数</span><span class="sxs-lookup"><span data-stu-id="3557f-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="3557f-111">已识别杂注的名称。</span><span class="sxs-lookup"><span data-stu-id="3557f-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="3557f-112">特定于杂注的参数。</span><span class="sxs-lookup"><span data-stu-id="3557f-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3557f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3557f-113">See Also</span></span>  
 [<span data-ttu-id="3557f-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3557f-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3557f-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3557f-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3557f-116">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="3557f-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [<span data-ttu-id="3557f-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="3557f-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
 [<span data-ttu-id="3557f-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="3557f-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
