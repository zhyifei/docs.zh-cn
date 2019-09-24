---
title: 源代码行标识符、文件标识符和路径标识符
description: 了解如何使用内置的F#标识符值，通过这些值可以访问代码中的源行号、目录和文件名。
ms.date: 05/16/2016
ms.openlocfilehash: f22c3dfb3cb106fbe45883ffd7de01feac30db00
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216749"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="d5a1d-103">源代码行标识符、文件标识符和路径标识符</span><span class="sxs-lookup"><span data-stu-id="d5a1d-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="d5a1d-104">标识符`__LINE__`， `__SOURCE_DIRECTORY__`和是内置值，使用这些值可以访问代码中的源行号、目录和文件名。`__SOURCE_FILE__`</span><span class="sxs-lookup"><span data-stu-id="d5a1d-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="d5a1d-105">语法</span><span class="sxs-lookup"><span data-stu-id="d5a1d-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="d5a1d-106">备注</span><span class="sxs-lookup"><span data-stu-id="d5a1d-106">Remarks</span></span>

<span data-ttu-id="d5a1d-107">其中每个值都有`string`类型。</span><span class="sxs-lookup"><span data-stu-id="d5a1d-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="d5a1d-108">下表汇总了中F#可用的源行、文件和路径标识符。</span><span class="sxs-lookup"><span data-stu-id="d5a1d-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="d5a1d-109">这些标识符不是预处理器宏;它们是编译器识别的内置值。</span><span class="sxs-lookup"><span data-stu-id="d5a1d-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="d5a1d-110">预定义标识符</span><span class="sxs-lookup"><span data-stu-id="d5a1d-110">Predefined identifier</span></span>|<span data-ttu-id="d5a1d-111">描述</span><span class="sxs-lookup"><span data-stu-id="d5a1d-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="d5a1d-112">计算结果为当前行号，考虑`#line`指令。</span><span class="sxs-lookup"><span data-stu-id="d5a1d-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="d5a1d-113">计算结果为源目录的当前完整路径，考虑`#line`指令。</span><span class="sxs-lookup"><span data-stu-id="d5a1d-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="d5a1d-114">计算结果为当前源文件名，而不包含其路径， `#line`考虑指令。</span><span class="sxs-lookup"><span data-stu-id="d5a1d-114">Evaluates to the current source file name, without its path, considering `#line` directives.</span></span>|

<span data-ttu-id="d5a1d-115">有关`#line`指令的详细信息，请参阅[编译器指令](compiler-directives.md)。</span><span class="sxs-lookup"><span data-stu-id="d5a1d-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="d5a1d-116">示例</span><span class="sxs-lookup"><span data-stu-id="d5a1d-116">Example</span></span>

<span data-ttu-id="d5a1d-117">下面的代码示例演示如何使用这些值。</span><span class="sxs-lookup"><span data-stu-id="d5a1d-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="d5a1d-118">输出：</span><span class="sxs-lookup"><span data-stu-id="d5a1d-118">Output:</span></span>

```console
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a><span data-ttu-id="d5a1d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5a1d-119">See also</span></span>

- [<span data-ttu-id="d5a1d-120">编译器指令</span><span class="sxs-lookup"><span data-stu-id="d5a1d-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="d5a1d-121">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="d5a1d-121">F# Language Reference</span></span>](index.md)
