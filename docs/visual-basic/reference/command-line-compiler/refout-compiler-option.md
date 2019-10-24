---
title: -refout （Visual Basic）
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 552e611f222bfcc3ce12520ecdb891fd7b8b21de
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775545"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="9acb4-102">-refout （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="9acb4-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="9acb4-103">-refout 选项指定应输出引用程序集的文件路径。</span><span class="sxs-lookup"><span data-stu-id="9acb4-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="9acb4-104">语法</span><span class="sxs-lookup"><span data-stu-id="9acb4-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="9acb4-105">自变量</span><span class="sxs-lookup"><span data-stu-id="9acb4-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="9acb4-106">引用程序集的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="9acb4-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="9acb4-107">它通常应位于主要程序集的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9acb4-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="9acb4-108">推荐约定（MSBuild 采用）是，将引用程序集放入与主程序集相关的“ref/”子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9acb4-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="9acb4-109">@No__t_0 中的所有文件夹都必须存在，编译器不会创建它们。</span><span class="sxs-lookup"><span data-stu-id="9acb4-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="9acb4-110">备注</span><span class="sxs-lookup"><span data-stu-id="9acb4-110">Remarks</span></span>

<span data-ttu-id="9acb4-111">从15.3 版开始 Visual Basic 支持 `-refout` 开关。</span><span class="sxs-lookup"><span data-stu-id="9acb4-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="9acb4-112">引用程序集是一种特殊类型的程序集，该程序集只包含表示库的公共 API 图面所需的最少元数据量。</span><span class="sxs-lookup"><span data-stu-id="9acb4-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="9acb4-113">它们包括在生成工具中引用程序集时所有重要成员的声明，但不包括对其 API 协定没有明显影响的私有成员的所有成员实现和声明。</span><span class="sxs-lookup"><span data-stu-id="9acb4-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="9acb4-114">有关详细信息，请参阅 .NET 中的[引用程序集](../../../standard/assembly/reference-assemblies.md)指南。</span><span class="sxs-lookup"><span data-stu-id="9acb4-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="9acb4-115">`-refout` 和 [`-refonly`](refonly-compiler-option.md) 选项互斥。</span><span class="sxs-lookup"><span data-stu-id="9acb4-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="9acb4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9acb4-116">See also</span></span>

- [<span data-ttu-id="9acb4-117">/refonly</span><span class="sxs-lookup"><span data-stu-id="9acb4-117">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="9acb4-118">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="9acb4-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="9acb4-119">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="9acb4-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
