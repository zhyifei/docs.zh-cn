---
title: -refout （Visual Basic）
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582875"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="e4399-102">-refout （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="e4399-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="e4399-103">-refout 选项指定应输出引用程序集的文件路径。</span><span class="sxs-lookup"><span data-stu-id="e4399-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="e4399-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4399-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="e4399-105">自变量</span><span class="sxs-lookup"><span data-stu-id="e4399-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="e4399-106">引用程序集的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="e4399-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="e4399-107">它通常应位于主要程序集的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e4399-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="e4399-108">推荐约定（MSBuild 采用）是，将引用程序集放入与主程序集相关的“ref/”子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="e4399-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="e4399-109">@No__t_0 中的所有文件夹都必须存在，编译器不会创建它们。</span><span class="sxs-lookup"><span data-stu-id="e4399-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4399-110">备注</span><span class="sxs-lookup"><span data-stu-id="e4399-110">Remarks</span></span>

<span data-ttu-id="e4399-111">从15.3 版开始 Visual Basic 支持 `-refout` 开关。</span><span class="sxs-lookup"><span data-stu-id="e4399-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="e4399-112">引用程序集是仅包含元数据的元数据程序集，但没有实现代码。</span><span class="sxs-lookup"><span data-stu-id="e4399-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="e4399-113">它们包括匿名类型之外的所有内容的类型和成员信息。</span><span class="sxs-lookup"><span data-stu-id="e4399-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="e4399-114">使用单个 `throw null` 语句替换其方法体。</span><span class="sxs-lookup"><span data-stu-id="e4399-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="e4399-115">使用 `throw null` 方法主体（而不是主体）的原因是，Peverify.exe 可以运行并通过（从而验证元数据的完整性）。</span><span class="sxs-lookup"><span data-stu-id="e4399-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="e4399-116">引用程序集包括程序集级别的[ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute)特性。</span><span class="sxs-lookup"><span data-stu-id="e4399-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="e4399-117">可以在源中指定此属性（之后编译器就不需要进行合成）。</span><span class="sxs-lookup"><span data-stu-id="e4399-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="e4399-118">由于此属性，运行时将拒绝加载引用程序集以便执行（但仍可以在只反射上下文中加载它们）。</span><span class="sxs-lookup"><span data-stu-id="e4399-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="e4399-119">反射程序集的工具需要确保它们将引用程序集作为仅反射加载;否则，运行时会引发 <xref:System.BadImageFormatException>。</span><span class="sxs-lookup"><span data-stu-id="e4399-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="e4399-120">`-refout` 和 [`-refonly`](refonly-compiler-option.md) 选项互斥。</span><span class="sxs-lookup"><span data-stu-id="e4399-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4399-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4399-121">See also</span></span>

- [<span data-ttu-id="e4399-122">/refonly</span><span class="sxs-lookup"><span data-stu-id="e4399-122">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="e4399-123">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="e4399-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e4399-124">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="e4399-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
