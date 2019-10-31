---
title: -refonly（C# 编译器选项）
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: 856b65d3b2217dbe5d53ecda00723b47247d80a4
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773855"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="99ecf-102">-refonly（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="99ecf-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="99ecf-103">-refonly 选项表示应输出引用程序集（而不是实现程序集）作为主输出  。</span><span class="sxs-lookup"><span data-stu-id="99ecf-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="99ecf-104">`-refonly` 参数以无提示方式禁用输出 PDB，因为无法执行引用程序集。</span><span class="sxs-lookup"><span data-stu-id="99ecf-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="99ecf-105">此选项对应于 MSBuild 的 [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) 项目属性。</span><span class="sxs-lookup"><span data-stu-id="99ecf-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="99ecf-106">语法</span><span class="sxs-lookup"><span data-stu-id="99ecf-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="99ecf-107">备注</span><span class="sxs-lookup"><span data-stu-id="99ecf-107">Remarks</span></span>

<span data-ttu-id="99ecf-108">引用程序集是一种特殊类型的程序集，它只包含表示库的公共 API 外围应用所需的最少元数据量。</span><span class="sxs-lookup"><span data-stu-id="99ecf-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="99ecf-109">它们包括在生成工具中引用程序集时所需的所有成员的声明，但不包括所有成员实现以及对其 API 协定没有明显影响的私有成员的声明。</span><span class="sxs-lookup"><span data-stu-id="99ecf-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="99ecf-110">有关详细信息，请参阅 .NET 指南中的[引用程序集](../../../standard/assembly/reference-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="99ecf-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="99ecf-111">`-refonly` 和 [`-refout`](refout-compiler-option.md) 选项互斥。</span><span class="sxs-lookup"><span data-stu-id="99ecf-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="99ecf-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="99ecf-112">See also</span></span>

- [<span data-ttu-id="99ecf-113">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="99ecf-113">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="99ecf-114">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="99ecf-114">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
