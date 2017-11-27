---
title: "源代码行标识符、文件标识符和路径标识符 (F#)"
description: "了解如何使用内置 F # 标识符的值使你能够访问源行号、 目录和在代码中的文件名称。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4cfe7439-275c-4d08-980b-784e240bbf29
ms.openlocfilehash: 44cc0914226c120f2b877ce3decd25caa6817eec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="7201a-104">源代码行标识符、文件标识符和路径标识符</span><span class="sxs-lookup"><span data-stu-id="7201a-104">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="7201a-105">标识符`__LINE__`，`__SOURCE_DIRECTORY__`和`__SOURCE_FILE__`是内置值，它们使你能够访问你的代码中的源行号、 目录和文件名称。</span><span class="sxs-lookup"><span data-stu-id="7201a-105">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>


## <a name="syntax"></a><span data-ttu-id="7201a-106">语法</span><span class="sxs-lookup"><span data-stu-id="7201a-106">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="7201a-107">备注</span><span class="sxs-lookup"><span data-stu-id="7201a-107">Remarks</span></span>
<span data-ttu-id="7201a-108">其中每个值具有类型`string`。</span><span class="sxs-lookup"><span data-stu-id="7201a-108">Each of these values has type `string`.</span></span>

<span data-ttu-id="7201a-109">下表总结了源行、 文件和 F # 中可用的路径标识符。</span><span class="sxs-lookup"><span data-stu-id="7201a-109">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="7201a-110">这些标识符不是预处理器宏;它们是由编译器识别的内置值。</span><span class="sxs-lookup"><span data-stu-id="7201a-110">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="7201a-111">预定义的标识符</span><span class="sxs-lookup"><span data-stu-id="7201a-111">Predefined identifier</span></span>|<span data-ttu-id="7201a-112">描述</span><span class="sxs-lookup"><span data-stu-id="7201a-112">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="7201a-113">计算结果为当前行号，考虑`#line`指令。</span><span class="sxs-lookup"><span data-stu-id="7201a-113">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="7201a-114">计算结果为当前的完整路径的源目录中，考虑`#line`指令。</span><span class="sxs-lookup"><span data-stu-id="7201a-114">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="7201a-115">计算结果为当前的源文件的名称，其路径中，考虑`#line`指令。</span><span class="sxs-lookup"><span data-stu-id="7201a-115">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="7201a-116">有关详细信息`#line`指令，请参阅[编译器指令](compiler-directives.md)。</span><span class="sxs-lookup"><span data-stu-id="7201a-116">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="7201a-117">示例</span><span class="sxs-lookup"><span data-stu-id="7201a-117">Example</span></span>

<span data-ttu-id="7201a-118">下面的代码示例演示如何将这些值。</span><span class="sxs-lookup"><span data-stu-id="7201a-118">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="7201a-119">输出：</span><span class="sxs-lookup"><span data-stu-id="7201a-119">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="7201a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7201a-120">See Also</span></span>
[<span data-ttu-id="7201a-121">编译器指令</span><span class="sxs-lookup"><span data-stu-id="7201a-121">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="7201a-122">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="7201a-122">F# Language Reference</span></span>](index.md)
