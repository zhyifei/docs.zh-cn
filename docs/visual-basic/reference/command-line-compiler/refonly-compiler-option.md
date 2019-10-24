---
title: -refonly （Visual Basic）
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775569"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="bb575-102">-refonly （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="bb575-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="bb575-103">**-Refonly**选项指示编译的主输出应为引用程序集，而不是实现程序集。</span><span class="sxs-lookup"><span data-stu-id="bb575-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="bb575-104">`-refonly` 参数以无提示方式禁用输出 PDB，因为无法执行引用程序集。</span><span class="sxs-lookup"><span data-stu-id="bb575-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="bb575-105">语法</span><span class="sxs-lookup"><span data-stu-id="bb575-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="bb575-106">备注</span><span class="sxs-lookup"><span data-stu-id="bb575-106">Remarks</span></span>

<span data-ttu-id="bb575-107">从15.3 版开始 Visual Basic 支持 `-refonly` 开关。</span><span class="sxs-lookup"><span data-stu-id="bb575-107">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="bb575-108">引用程序集是一种特殊类型的程序集，该程序集只包含表示库的公共 API 图面所需的最少元数据量。</span><span class="sxs-lookup"><span data-stu-id="bb575-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="bb575-109">它们包括在生成工具中引用程序集时所有重要成员的声明，但不包括对其 API 协定没有明显影响的私有成员的所有成员实现和声明。</span><span class="sxs-lookup"><span data-stu-id="bb575-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="bb575-110">有关详细信息，请参阅 .NET 中的[引用程序集](../../../standard/assembly/reference-assemblies.md)指南。</span><span class="sxs-lookup"><span data-stu-id="bb575-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="bb575-111">`-refonly` 和 [`-refout`](refout-compiler-option.md) 选项互斥。</span><span class="sxs-lookup"><span data-stu-id="bb575-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb575-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb575-112">See also</span></span>

- [<span data-ttu-id="bb575-113">/refout</span><span class="sxs-lookup"><span data-stu-id="bb575-113">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="bb575-114">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="bb575-114">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="bb575-115">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="bb575-115">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
