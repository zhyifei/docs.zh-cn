---
title: '#pragma - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 65ca38ff6993117b6ed9f716d4ac93ba2d4a9ddf
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69605667"
---
# <a name="pragma-c-reference"></a><span data-ttu-id="e3621-102">#pragma（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e3621-102">#pragma (C# Reference)</span></span>
<span data-ttu-id="e3621-103">`#pragma` 为编译器给出特殊指令以编译它所在的文件。</span><span class="sxs-lookup"><span data-stu-id="e3621-103">`#pragma` gives the compiler special instructions for the compilation of the file in which it appears.</span></span> <span data-ttu-id="e3621-104">这些指令必须受编译器支持。</span><span class="sxs-lookup"><span data-stu-id="e3621-104">The instructions must be supported by the compiler.</span></span> <span data-ttu-id="e3621-105">即是说，不可使用 `#pragma` 创建自定义处理指令。</span><span class="sxs-lookup"><span data-stu-id="e3621-105">In other words, you cannot use `#pragma` to create custom preprocessing instructions.</span></span> <span data-ttu-id="e3621-106">Microsoft C# 编译器支持以下两种 `#pragma` 指令：</span><span class="sxs-lookup"><span data-stu-id="e3621-106">The Microsoft C# compiler supports the following two `#pragma` instructions:</span></span>  
  
 [<span data-ttu-id="e3621-107">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="e3621-107">#pragma warning</span></span>](./preprocessor-pragma-warning.md)  
  
 [<span data-ttu-id="e3621-108">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="e3621-108">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a><span data-ttu-id="e3621-109">语法</span><span class="sxs-lookup"><span data-stu-id="e3621-109">Syntax</span></span>  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3621-110">参数</span><span class="sxs-lookup"><span data-stu-id="e3621-110">Parameters</span></span>  
 `pragma-name`  
 <span data-ttu-id="e3621-111">已识别杂注的名称。</span><span class="sxs-lookup"><span data-stu-id="e3621-111">The name of a recognized pragma.</span></span>  
  
 `pragma-arguments`  
 <span data-ttu-id="e3621-112">特定于杂注的参数。</span><span class="sxs-lookup"><span data-stu-id="e3621-112">Pragma-specific arguments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3621-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3621-113">See also</span></span>

- [<span data-ttu-id="e3621-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e3621-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e3621-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e3621-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e3621-116">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="e3621-116">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="e3621-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="e3621-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="e3621-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="e3621-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)
