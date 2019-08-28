---
title: -refonly（C# 编译器选项）
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: eb62f98c5d548fe3583d3422eb7b6020a82c296a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606481"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="1139a-102">-refonly（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="1139a-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="1139a-103">-refonly 选项表示应输出引用程序集（而不是实现程序集）作为主输出  。</span><span class="sxs-lookup"><span data-stu-id="1139a-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="1139a-104">`-refonly` 参数以无提示方式禁用输出 PDB，因为无法执行引用程序集。</span><span class="sxs-lookup"><span data-stu-id="1139a-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="1139a-105">此选项对应于 MSBuild 的 [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) 项目属性。</span><span class="sxs-lookup"><span data-stu-id="1139a-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="1139a-106">语法</span><span class="sxs-lookup"><span data-stu-id="1139a-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="1139a-107">备注</span><span class="sxs-lookup"><span data-stu-id="1139a-107">Remarks</span></span>

<span data-ttu-id="1139a-108">仅包含元数据的程序集会将方法主体替换为一个 `throw null` 主体，但包括除匿名类型以外的所有成员。</span><span class="sxs-lookup"><span data-stu-id="1139a-108">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="1139a-109">使用 `throw null` 主体（而非不使用主体）的原因在于，这样做可以运行和传递 PEVerify（从而验证元数据的完整性）。</span><span class="sxs-lookup"><span data-stu-id="1139a-109">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="1139a-110">引用程序集包括程序集级 `ReferenceAssembly` 属性。</span><span class="sxs-lookup"><span data-stu-id="1139a-110">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="1139a-111">可以在源中指定此属性（之后编译器就不需要进行合成）。</span><span class="sxs-lookup"><span data-stu-id="1139a-111">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="1139a-112">由于有此属性，运行时会拒绝加载用于执行的引用程序集（但仍可在仅限反射的模式下加载）。</span><span class="sxs-lookup"><span data-stu-id="1139a-112">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="1139a-113">在程序集上反射的工具需要确保仅将引用程序集加载为反射模式，否则将生成运行时 typeload 错误。</span><span class="sxs-lookup"><span data-stu-id="1139a-113">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="1139a-114">引用程序集进一步从仅包含元数据的程序集中删除元数据（私有成员）：</span><span class="sxs-lookup"><span data-stu-id="1139a-114">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="1139a-115">引用程序集只包含在 API 外围应用中所需的引用。</span><span class="sxs-lookup"><span data-stu-id="1139a-115">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="1139a-116">实际程序集可能包含与特定实现相关的其他引用。</span><span class="sxs-lookup"><span data-stu-id="1139a-116">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="1139a-117">例如，`class C { private void M() { dynamic d = 1; ... } }` 的引用程序集不引用 `dynamic` 所需的任何类型。</span><span class="sxs-lookup"><span data-stu-id="1139a-117">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="1139a-118">删除私有函数成员（方法、属性和事件），前提是这不会对编译造成显著影响。</span><span class="sxs-lookup"><span data-stu-id="1139a-118">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="1139a-119">如果没有 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 属性，也请删除内部函数成员。</span><span class="sxs-lookup"><span data-stu-id="1139a-119">If there are no <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="1139a-120">但保留引用程序集中的所有类型（包括私有或嵌套类型）。</span><span class="sxs-lookup"><span data-stu-id="1139a-120">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="1139a-121">保留所有属性（甚至是内部属性）。</span><span class="sxs-lookup"><span data-stu-id="1139a-121">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="1139a-122">保留所有虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="1139a-122">All virtual methods are kept.</span></span> <span data-ttu-id="1139a-123">保留显式接口实现。</span><span class="sxs-lookup"><span data-stu-id="1139a-123">Explicit interface implementations are kept.</span></span> <span data-ttu-id="1139a-124">保留显式实现的属性和事件，因为它们的访问器是虚拟的（因此予以保留）。</span><span class="sxs-lookup"><span data-stu-id="1139a-124">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="1139a-125">保留结构的所有字段。</span><span class="sxs-lookup"><span data-stu-id="1139a-125">All fields of a struct are kept.</span></span> <span data-ttu-id="1139a-126">（这是 post-C#-7.1 优化候选项）</span><span class="sxs-lookup"><span data-stu-id="1139a-126">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="1139a-127">`-refonly` 和 [`-refout`](refout-compiler-option.md) 选项互斥。</span><span class="sxs-lookup"><span data-stu-id="1139a-127">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="1139a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="1139a-128">See also</span></span>

- [<span data-ttu-id="1139a-129">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="1139a-129">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="1139a-130">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="1139a-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
