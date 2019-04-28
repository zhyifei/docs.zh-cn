---
title: -deterministic
ms.date: 04/11/2018
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
ms.openlocfilehash: 95c9add0521208ef04ff47c071a2e04abc968f27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61648732"
---
# <a name="-deterministic"></a><span data-ttu-id="9f7bd-102">-deterministic</span><span class="sxs-lookup"><span data-stu-id="9f7bd-102">-deterministic</span></span>

<span data-ttu-id="9f7bd-103">如果输入相同，则会导致编译器生成的程序集其逐字节输出在整个编译期间中相同。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f7bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f7bd-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="9f7bd-105">备注</span><span class="sxs-lookup"><span data-stu-id="9f7bd-105">Remarks</span></span>

<span data-ttu-id="9f7bd-106">默认情况下，一组给定输入的编译器输出是唯一的，因为编译器会添加时间戳和随意数字生成的 GUID。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="9f7bd-107">使用 `-deterministic` 选项生成确定性的程序集，只要输入保持不变，该程序集的二进制内容在整个编译中都是相同的。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="9f7bd-108">出于确定性目的，编译器会考虑以下输入：</span><span class="sxs-lookup"><span data-stu-id="9f7bd-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="9f7bd-109">命令行参数序列。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="9f7bd-110">编译器 .rsp 响应文件的内容。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="9f7bd-111">所用编译器的精确版本及其引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="9f7bd-112">当前目录路径。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-112">The current directory path.</span></span>
- <span data-ttu-id="9f7bd-113">直接或间接地显式传递到编译器的所有文件的二进制内容，包括：</span><span class="sxs-lookup"><span data-stu-id="9f7bd-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span>
  - <span data-ttu-id="9f7bd-114">源文件</span><span class="sxs-lookup"><span data-stu-id="9f7bd-114">Source files</span></span>
  - <span data-ttu-id="9f7bd-115">引用的程序集</span><span class="sxs-lookup"><span data-stu-id="9f7bd-115">Referenced assemblies</span></span>
  - <span data-ttu-id="9f7bd-116">引用的模块</span><span class="sxs-lookup"><span data-stu-id="9f7bd-116">Referenced modules</span></span>
  - <span data-ttu-id="9f7bd-117">资源</span><span class="sxs-lookup"><span data-stu-id="9f7bd-117">Resources</span></span>
  - <span data-ttu-id="9f7bd-118">强名称密钥文件</span><span class="sxs-lookup"><span data-stu-id="9f7bd-118">The strong name key file</span></span>
  - <span data-ttu-id="9f7bd-119">@ 响应文件</span><span class="sxs-lookup"><span data-stu-id="9f7bd-119">@ response files</span></span>
  - <span data-ttu-id="9f7bd-120">分析器</span><span class="sxs-lookup"><span data-stu-id="9f7bd-120">Analyzers</span></span>
  - <span data-ttu-id="9f7bd-121">规则集</span><span class="sxs-lookup"><span data-stu-id="9f7bd-121">Rulesets</span></span>
  - <span data-ttu-id="9f7bd-122">分析器可能使用的其他文件</span><span class="sxs-lookup"><span data-stu-id="9f7bd-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="9f7bd-123">当前区域性（针对生成诊断和异常消息的语言）。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="9f7bd-124">在未指定编码情况下使用的默认编码（或当前代码页）。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="9f7bd-125">编译器搜索路径（例如，由`/lib` 或 `/recurse` 指定）上文件是否存在及其内容。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="9f7bd-126">运行编译器的 CLR 平台。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="9f7bd-127">`%LIBPATH%` 的值，该值会影响分析器的依赖项加载。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="9f7bd-128">当源公开可用时，可使用确定性编译来确定是否从可信源编译二进制内容。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="9f7bd-129">它还可有效用于连续生成系统，确定是否需要执行依赖于二进制内容更改的生成步骤。</span><span class="sxs-lookup"><span data-stu-id="9f7bd-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f7bd-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f7bd-130">See also</span></span>

- [<span data-ttu-id="9f7bd-131">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="9f7bd-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9f7bd-132">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="9f7bd-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
