---
title: -refout（C# 编译器选项）
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: f48316a1e6f657e3bd0190d269dfe0e875a833d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "72771757"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="6a3a7-102">-refout（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="6a3a7-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="6a3a7-103">-refout 选项指定应输出引用程序集的文件路径  。</span><span class="sxs-lookup"><span data-stu-id="6a3a7-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="6a3a7-104">这在 Emit API 中转换为 `metadataPeStream`。</span><span class="sxs-lookup"><span data-stu-id="6a3a7-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="6a3a7-105">此选项对应于 MSBuild 的 [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) 项目属性。</span><span class="sxs-lookup"><span data-stu-id="6a3a7-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a3a7-106">语法</span><span class="sxs-lookup"><span data-stu-id="6a3a7-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="6a3a7-107">参数</span><span class="sxs-lookup"><span data-stu-id="6a3a7-107">Arguments</span></span>

 <span data-ttu-id="6a3a7-108">`filepath` - 引用程序集的文件路径。</span><span class="sxs-lookup"><span data-stu-id="6a3a7-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="6a3a7-109">通常情况下，应与主程序集的路径匹配。</span><span class="sxs-lookup"><span data-stu-id="6a3a7-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="6a3a7-110">推荐约定（MSBuild 采用）是，将引用程序集放入与主程序集相关的“ref/”子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6a3a7-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a3a7-111">备注</span><span class="sxs-lookup"><span data-stu-id="6a3a7-111">Remarks</span></span>

<span data-ttu-id="6a3a7-112">引用程序集是一种特殊类型的程序集，它只包含表示库的公共 API 外围应用所需的最少元数据量。</span><span class="sxs-lookup"><span data-stu-id="6a3a7-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="6a3a7-113">它们包括在生成工具中引用程序集时所需的所有成员的声明，但不包括所有成员实现以及对其 API 协定没有明显影响的私有成员的声明。</span><span class="sxs-lookup"><span data-stu-id="6a3a7-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="6a3a7-114">有关详细信息，请参阅 .NET 指南中的[引用程序集](../../../standard/assembly/reference-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="6a3a7-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="6a3a7-115">`-refout` 和 [`-refonly`](refonly-compiler-option.md) 选项互斥。</span><span class="sxs-lookup"><span data-stu-id="6a3a7-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a3a7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a3a7-116">See also</span></span>

- [<span data-ttu-id="6a3a7-117">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="6a3a7-117">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6a3a7-118">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="6a3a7-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
