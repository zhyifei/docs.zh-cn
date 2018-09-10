---
title: -refout（C# 编译器选项）
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: e204a053f6f68a4b848d22c95c98f04edff58716
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506620"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="c9066-102">-refout（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="c9066-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="c9066-103">-refout 选项指定应输出引用程序集的文件路径。</span><span class="sxs-lookup"><span data-stu-id="c9066-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="c9066-104">这在 Emit API 中转换为 `metadataPeStream`。</span><span class="sxs-lookup"><span data-stu-id="c9066-104">This translates to `metadataPeStream` in the Emit API.</span></span>

## <a name="syntax"></a><span data-ttu-id="c9066-105">语法</span><span class="sxs-lookup"><span data-stu-id="c9066-105">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="c9066-106">自变量</span><span class="sxs-lookup"><span data-stu-id="c9066-106">Arguments</span></span>

 <span data-ttu-id="c9066-107">`filepath` - 引用程序集的文件路径。</span><span class="sxs-lookup"><span data-stu-id="c9066-107">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="c9066-108">通常情况下，应与主程序集的路径匹配。</span><span class="sxs-lookup"><span data-stu-id="c9066-108">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="c9066-109">推荐约定（MSBuild 采用）是，将引用程序集放入与主程序集相关的“ref/”子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c9066-109">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9066-110">备注</span><span class="sxs-lookup"><span data-stu-id="c9066-110">Remarks</span></span>

<span data-ttu-id="c9066-111">仅包含元数据的程序集会将方法主体替换为一个 `throw null` 主体，但包括除匿名类型以外的所有成员。</span><span class="sxs-lookup"><span data-stu-id="c9066-111">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="c9066-112">使用 `throw null` 主体（而非不使用主体）的原因在于，这样做可以运行和传递 PEVerify（从而验证元数据的完整性）。</span><span class="sxs-lookup"><span data-stu-id="c9066-112">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="c9066-113">引用程序集包括程序集级 `ReferenceAssembly` 属性。</span><span class="sxs-lookup"><span data-stu-id="c9066-113">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="c9066-114">可以在源中指定此属性（之后编译器就不需要进行合成）。</span><span class="sxs-lookup"><span data-stu-id="c9066-114">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="c9066-115">由于有此属性，运行时会拒绝加载用于执行的引用程序集（但仍可在仅限反射的模式下加载）。</span><span class="sxs-lookup"><span data-stu-id="c9066-115">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="c9066-116">在程序集上反射的工具需要确保仅将引用程序集加载为反射模式，否则将生成运行时 typeload 错误。</span><span class="sxs-lookup"><span data-stu-id="c9066-116">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="c9066-117">引用程序集进一步从仅包含元数据的程序集中删除元数据（私有成员）：</span><span class="sxs-lookup"><span data-stu-id="c9066-117">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="c9066-118">引用程序集只包含在 API 外围应用中所需的引用。</span><span class="sxs-lookup"><span data-stu-id="c9066-118">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="c9066-119">实际程序集可能包含与特定实现相关的其他引用。</span><span class="sxs-lookup"><span data-stu-id="c9066-119">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="c9066-120">例如，`class C { private void M() { dynamic d = 1; ... } }` 的引用程序集不引用 `dynamic` 所需的任何类型。</span><span class="sxs-lookup"><span data-stu-id="c9066-120">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="c9066-121">删除私有函数成员（方法、属性和事件），前提是这不会对编译造成显著影响。</span><span class="sxs-lookup"><span data-stu-id="c9066-121">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="c9066-122">如果没有 `InternalsVisibleTo` 属性，也请删除内部函数成员。</span><span class="sxs-lookup"><span data-stu-id="c9066-122">If there are no `InternalsVisibleTo` attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="c9066-123">但保留引用程序集中的所有类型（包括私有或嵌套类型）。</span><span class="sxs-lookup"><span data-stu-id="c9066-123">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="c9066-124">保留所有属性（甚至是内部属性）。</span><span class="sxs-lookup"><span data-stu-id="c9066-124">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="c9066-125">保留所有虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="c9066-125">All virtual methods are kept.</span></span> <span data-ttu-id="c9066-126">保留显式接口实现。</span><span class="sxs-lookup"><span data-stu-id="c9066-126">Explicit interface implementations are kept.</span></span> <span data-ttu-id="c9066-127">保留显式实现的属性和事件，因为它们的访问器是虚拟的（因此予以保留）。</span><span class="sxs-lookup"><span data-stu-id="c9066-127">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="c9066-128">保留结构的所有字段。</span><span class="sxs-lookup"><span data-stu-id="c9066-128">All fields of a struct are kept.</span></span> <span data-ttu-id="c9066-129">（这是 post-C#-7.1 优化候选项）</span><span class="sxs-lookup"><span data-stu-id="c9066-129">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="c9066-130">`-refout` 和 [`-refonly`](refonly-compiler-option.md) 选项互斥。</span><span class="sxs-lookup"><span data-stu-id="c9066-130">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9066-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9066-131">See Also</span></span>

- [<span data-ttu-id="c9066-132">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="c9066-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="c9066-133">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="c9066-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
