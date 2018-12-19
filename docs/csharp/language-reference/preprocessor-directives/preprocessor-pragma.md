---
title: '#pragma - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 65867bc441711193f93142d1c65122b6bc60c25d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241822"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="b2e42-102">#pragma（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b2e42-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="b2e42-103">`#pragma` 为编译器给出特殊指令以编译它所在的文件。</span><span class="sxs-lookup"><span data-stu-id="b2e42-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="b2e42-104">这些指令必须受编译器支持。</span><span class="sxs-lookup"><span data-stu-id="b2e42-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="b2e42-105">即是说，不可使用 `#pragma` 创建自定义处理指令。</span><span class="sxs-lookup"><span data-stu-id="b2e42-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="b2e42-106">Microsoft C# 编译器支持以下两种 `#pragma` 指令：</span><span class="sxs-lookup"><span data-stu-id="b2e42-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="b2e42-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="b2e42-107">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="b2e42-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="b2e42-108">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="b2e42-109">语法</span><span class="sxs-lookup"><span data-stu-id="b2e42-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2e42-110">参数</span><span class="sxs-lookup"><span data-stu-id="b2e42-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="b2e42-111">已识别杂注的名称。</span><span class="sxs-lookup"><span data-stu-id="b2e42-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="b2e42-112">特定于杂注的参数。</span><span class="sxs-lookup"><span data-stu-id="b2e42-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e42-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2e42-113">See Also</span></span>

- [<span data-ttu-id="b2e42-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b2e42-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b2e42-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b2e42-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b2e42-116">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="b2e42-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
- [<span data-ttu-id="b2e42-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="b2e42-117">#pragma warning</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)  
- [<span data-ttu-id="b2e42-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="b2e42-118">#pragma checksum</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-checksum.md)
