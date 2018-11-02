---
title: 源代码行标识符、文件标识符和路径标识符 (F#)
description: '了解如何使用内置的 F # 标识符值，使你能够访问源行号、 目录和文件名称在代码中。'
ms.date: 05/16/2016
ms.openlocfilehash: 14f710d1412c3420ec627dc30216ba2e89f16bcd
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43865122"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="b3132-103">源代码行标识符、文件标识符和路径标识符</span><span class="sxs-lookup"><span data-stu-id="b3132-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="b3132-104">标识符`__LINE__`，`__SOURCE_DIRECTORY__`和`__SOURCE_FILE__`是内置使你能够访问你的代码中的源行号、 目录和文件名称的值。</span><span class="sxs-lookup"><span data-stu-id="b3132-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3132-105">语法</span><span class="sxs-lookup"><span data-stu-id="b3132-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="b3132-106">备注</span><span class="sxs-lookup"><span data-stu-id="b3132-106">Remarks</span></span>

<span data-ttu-id="b3132-107">每个值具有类型`string`。</span><span class="sxs-lookup"><span data-stu-id="b3132-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="b3132-108">下表总结了源行、 文件和路径标识符具有在 F # 中可用。</span><span class="sxs-lookup"><span data-stu-id="b3132-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="b3132-109">这些标识符不是预处理器宏;它们是由编译器识别的内置值。</span><span class="sxs-lookup"><span data-stu-id="b3132-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="b3132-110">预定义的标识符</span><span class="sxs-lookup"><span data-stu-id="b3132-110">Predefined identifier</span></span>|<span data-ttu-id="b3132-111">描述</span><span class="sxs-lookup"><span data-stu-id="b3132-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="b3132-112">计算结果为当前行号，考虑`#line`指令。</span><span class="sxs-lookup"><span data-stu-id="b3132-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="b3132-113">计算结果为当前源目录的完整路径考虑`#line`指令。</span><span class="sxs-lookup"><span data-stu-id="b3132-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="b3132-114">计算结果为当前的源代码文件的名称，其路径中，考虑`#line`指令。</span><span class="sxs-lookup"><span data-stu-id="b3132-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="b3132-115">有关详细信息`#line`指令，请参阅[编译器指令](compiler-directives.md)。</span><span class="sxs-lookup"><span data-stu-id="b3132-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="b3132-116">示例</span><span class="sxs-lookup"><span data-stu-id="b3132-116">Example</span></span>

<span data-ttu-id="b3132-117">下面的代码示例演示如何将这些值。</span><span class="sxs-lookup"><span data-stu-id="b3132-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="b3132-118">输出：</span><span class="sxs-lookup"><span data-stu-id="b3132-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="b3132-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3132-119">See also</span></span>

- [<span data-ttu-id="b3132-120">编译器指令</span><span class="sxs-lookup"><span data-stu-id="b3132-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="b3132-121">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="b3132-121">F# Language Reference</span></span>](index.md)
