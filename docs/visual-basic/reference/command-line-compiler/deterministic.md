---
title: -确定性
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 273abf8811f04cd7f58599ce3421ca1f17c740d9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a><span data-ttu-id="60f15-102">-确定性</span><span class="sxs-lookup"><span data-stu-id="60f15-102">-deterministic</span></span>

<span data-ttu-id="60f15-103">使编译器生成的程序集针对同一个输入编译都是相同的字节的字节输出。</span><span class="sxs-lookup"><span data-stu-id="60f15-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="60f15-104">语法</span><span class="sxs-lookup"><span data-stu-id="60f15-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="60f15-105">备注</span><span class="sxs-lookup"><span data-stu-id="60f15-105">Remarks</span></span>

<span data-ttu-id="60f15-106">默认情况下，从给定的一组输入编译器输出是唯一的因为编译器将添加的时间戳和从随机数生成的 GUID。</span><span class="sxs-lookup"><span data-stu-id="60f15-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="60f15-107">你使用`-deterministic`选项来生成*确定性的程序集*，其中一个，只要输入保持不变，其二进制内容是跨编译相同。</span><span class="sxs-lookup"><span data-stu-id="60f15-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="60f15-108">编译器认为出于确定性目的的以下输入：</span><span class="sxs-lookup"><span data-stu-id="60f15-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="60f15-109">命令行参数的序列。</span><span class="sxs-lookup"><span data-stu-id="60f15-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="60f15-110">编译器的.rsp 响应文件的内容。</span><span class="sxs-lookup"><span data-stu-id="60f15-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="60f15-111">使用，则编译器的精确版本和其引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="60f15-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="60f15-112">当前的目录路径。</span><span class="sxs-lookup"><span data-stu-id="60f15-112">The current directory path.</span></span>
- <span data-ttu-id="60f15-113">所有文件的二进制内容显式传递到编译器直接或间接包括：</span><span class="sxs-lookup"><span data-stu-id="60f15-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span> 
    - <span data-ttu-id="60f15-114">源文件</span><span class="sxs-lookup"><span data-stu-id="60f15-114">Source files</span></span>
    - <span data-ttu-id="60f15-115">引用的程序集</span><span class="sxs-lookup"><span data-stu-id="60f15-115">Referenced assemblies</span></span>
    - <span data-ttu-id="60f15-116">引用的模块</span><span class="sxs-lookup"><span data-stu-id="60f15-116">Referenced modules</span></span>
    - <span data-ttu-id="60f15-117">资源</span><span class="sxs-lookup"><span data-stu-id="60f15-117">Resources</span></span>
    - <span data-ttu-id="60f15-118">强名称密钥文件</span><span class="sxs-lookup"><span data-stu-id="60f15-118">The strong name key file</span></span>
    - <span data-ttu-id="60f15-119">@ 响应文件</span><span class="sxs-lookup"><span data-stu-id="60f15-119">@ response files</span></span>
    - <span data-ttu-id="60f15-120">分析器</span><span class="sxs-lookup"><span data-stu-id="60f15-120">Analyzers</span></span>
    - <span data-ttu-id="60f15-121">规则集</span><span class="sxs-lookup"><span data-stu-id="60f15-121">Rulesets</span></span>
    - <span data-ttu-id="60f15-122">可能由分析器的其他文件</span><span class="sxs-lookup"><span data-stu-id="60f15-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="60f15-123">（用于诊断和异常生成消息的语言） 的当前区域性。</span><span class="sxs-lookup"><span data-stu-id="60f15-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="60f15-124">默认编码 （或当前代码页） 如果未指定的编码。</span><span class="sxs-lookup"><span data-stu-id="60f15-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="60f15-125">是否存在、 不存在，以及编译器的搜索路径上的文件的内容 (例如，由指定`/lib`或`/recurse`)。</span><span class="sxs-lookup"><span data-stu-id="60f15-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="60f15-126">在其运行编译器 CLR 平台。</span><span class="sxs-lookup"><span data-stu-id="60f15-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="60f15-127">值`%LIBPATH%`，这可能会影响分析器的依赖项加载。</span><span class="sxs-lookup"><span data-stu-id="60f15-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="60f15-128">当源公开可用时，确定性编译可以用于建立从受信任的源是否已编译二进制文件。</span><span class="sxs-lookup"><span data-stu-id="60f15-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="60f15-129">它还可用于确定是否依赖于对二进制文件的更改的生成步骤需要执行连续生成系统中有用。</span><span class="sxs-lookup"><span data-stu-id="60f15-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="60f15-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="60f15-130">See Also</span></span>
[<span data-ttu-id="60f15-131">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="60f15-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
[<span data-ttu-id="60f15-132">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="60f15-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
