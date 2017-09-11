---
title: "#<a name=\"pragma-c-reference\"></a>pragma（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e03fc387b105c1dee3b7fed93263ad8ef22d5934
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="pragma-c-reference"></a><span data-ttu-id="c4aed-102">#pragma（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c4aed-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="c4aed-103">`#pragma` 为编译器给出特殊指令以编译它所在的文件。</span><span class="sxs-lookup"><span data-stu-id="c4aed-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="c4aed-104">这些指令必须受编译器支持。</span><span class="sxs-lookup"><span data-stu-id="c4aed-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="c4aed-105">即是说，不可使用 `#pragma` 创建自定义处理指令。</span><span class="sxs-lookup"><span data-stu-id="c4aed-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="c4aed-106">Microsoft C# 编译器支持以下两种 `#pragma` 指令：</span><span class="sxs-lookup"><span data-stu-id="c4aed-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="c4aed-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="c4aed-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="c4aed-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="c4aed-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="c4aed-109">语法</span><span class="sxs-lookup"><span data-stu-id="c4aed-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4aed-110">参数</span><span class="sxs-lookup"><span data-stu-id="c4aed-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="c4aed-111">已识别杂注的名称。</span><span class="sxs-lookup"><span data-stu-id="c4aed-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="c4aed-112">特定于杂注的参数。</span><span class="sxs-lookup"><span data-stu-id="c4aed-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4aed-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4aed-113">See Also</span></span>  
 <span data-ttu-id="c4aed-114">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4aed-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c4aed-115">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4aed-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c4aed-116">[C# 预处理器指令](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4aed-116">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 <span data-ttu-id="c4aed-117">[#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) </span><span class="sxs-lookup"><span data-stu-id="c4aed-117">[#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) </span></span>  
 [<span data-ttu-id="c4aed-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="c4aed-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)

