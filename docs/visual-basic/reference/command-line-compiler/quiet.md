---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: a22773e2e37eb60ab6f1e88305266f41764311e7
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612584"
---
# <a name="-quiet"></a><span data-ttu-id="a31e4-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="a31e4-102">-quiet</span></span>

<span data-ttu-id="a31e4-103">阻止编译器显示与语法相关的错误和警告的代码。</span><span class="sxs-lookup"><span data-stu-id="a31e4-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="a31e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="a31e4-104">Syntax</span></span>

```
-quiet
```

## <a name="remarks"></a><span data-ttu-id="a31e4-105">备注</span><span class="sxs-lookup"><span data-stu-id="a31e4-105">Remarks</span></span>

<span data-ttu-id="a31e4-106">默认情况，`-quiet` 是无效的。</span><span class="sxs-lookup"><span data-stu-id="a31e4-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="a31e4-107">当编译器报告相关的语法错误或警告时，它还将输出从源代码行。</span><span class="sxs-lookup"><span data-stu-id="a31e4-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="a31e4-108">对于分析编译器输出的应用程序，它可能会更方便的编译器输出的诊断的文本。</span><span class="sxs-lookup"><span data-stu-id="a31e4-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="a31e4-109">在以下示例中，`Module1`输出的错误包括源代码，而无需在编译时`-quiet`。</span><span class="sxs-lookup"><span data-stu-id="a31e4-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="a31e4-110">输出：</span><span class="sxs-lookup"><span data-stu-id="a31e4-110">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="a31e4-111">使用编译`-quiet`，编译器只输出如下：</span><span class="sxs-lookup"><span data-stu-id="a31e4-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="a31e4-112">`-quiet`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。</span><span class="sxs-lookup"><span data-stu-id="a31e4-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="a31e4-113">示例</span><span class="sxs-lookup"><span data-stu-id="a31e4-113">Example</span></span>

<span data-ttu-id="a31e4-114">下面的代码编译`T2.vb`，不会显示相关的语法的编译器诊断的代码：</span><span class="sxs-lookup"><span data-stu-id="a31e4-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="a31e4-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a31e4-115">See also</span></span>

- [<span data-ttu-id="a31e4-116">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="a31e4-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a31e4-117">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="a31e4-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
