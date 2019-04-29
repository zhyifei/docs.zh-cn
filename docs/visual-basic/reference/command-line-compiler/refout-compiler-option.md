---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: f2cdd228d8ce1912abbbe888c29c42f29299ebba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788786"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="63af3-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63af3-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="63af3-103">-refout 选项指定应输出引用程序集的文件路径。</span><span class="sxs-lookup"><span data-stu-id="63af3-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="63af3-104">语法</span><span class="sxs-lookup"><span data-stu-id="63af3-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="63af3-105">自变量</span><span class="sxs-lookup"><span data-stu-id="63af3-105">Arguments</span></span>

 <span data-ttu-id="63af3-106">`filepath` 路径和文件名的引用程序集。</span><span class="sxs-lookup"><span data-stu-id="63af3-106">`filepath` The path and filename of the reference assembly.</span></span> <span data-ttu-id="63af3-107">它通常应主要程序集的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="63af3-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="63af3-108">推荐约定（MSBuild 采用）是，将引用程序集放入与主程序集相关的“ref/”子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="63af3-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="63af3-109">中的所有文件夹`filepath`必须存在; 编译器不会创建它们。</span><span class="sxs-lookup"><span data-stu-id="63af3-109">All folders in `filepath` must exist; the compiler does not create them.</span></span> 

## <a name="remarks"></a><span data-ttu-id="63af3-110">备注</span><span class="sxs-lookup"><span data-stu-id="63af3-110">Remarks</span></span>

<span data-ttu-id="63af3-111">Visual Basic 支持`-refout`切换从版本 15.3 开始。</span><span class="sxs-lookup"><span data-stu-id="63af3-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="63af3-112">引用程序集是包含元数据，但没有实现代码的仅限元数据的程序集。</span><span class="sxs-lookup"><span data-stu-id="63af3-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="63af3-113">它们包括匿名类型以外的所有内容的类型和成员信息。</span><span class="sxs-lookup"><span data-stu-id="63af3-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="63af3-114">方法主体替换为单个`throw null`语句。</span><span class="sxs-lookup"><span data-stu-id="63af3-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="63af3-115">使用的原因`throw null`（而不是不使用主体） 的方法体，以便可以运行 PEVerify 并将其传递 （从而验证元数据的完整性）。</span><span class="sxs-lookup"><span data-stu-id="63af3-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="63af3-116">引用程序集包括程序集级别[ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="63af3-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="63af3-117">可以在源中指定此属性（之后编译器就不需要进行合成）。</span><span class="sxs-lookup"><span data-stu-id="63af3-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="63af3-118">由于有此属性中，运行时拒绝加载用于执行引用程序集 （但仍可在仅限反射上下文中加载）。</span><span class="sxs-lookup"><span data-stu-id="63af3-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="63af3-119">在程序集反映的工具需要确保它们的加载为仅反射; 的引用程序集否则，运行时会引发<xref:System.BadImageFormatException>。</span><span class="sxs-lookup"><span data-stu-id="63af3-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="63af3-120">`-refout` 和 [`-refonly`](refonly-compiler-option.md) 选项互斥。</span><span class="sxs-lookup"><span data-stu-id="63af3-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="63af3-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="63af3-121">See also</span></span>

- [<span data-ttu-id="63af3-122">/refonly</span><span class="sxs-lookup"><span data-stu-id="63af3-122">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="63af3-123">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="63af3-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="63af3-124">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="63af3-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
