---
title: 按连续键对结果进行分组（C# 中的 LINQ）
description: 如何使用 C# 中的 LINQ 按连续键对结果进行分组。
ms.date: 08/14/2018
ms.assetid: cbda9c08-151b-4c9e-82f7-c3d7f3dac66b
ms.openlocfilehash: b5753c85bb07be4fc84b78a299eece961969ff9d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483997"
---
# <a name="group-results-by-contiguous-keys"></a><span data-ttu-id="2d08a-103">按连续键对结果进行分组</span><span class="sxs-lookup"><span data-stu-id="2d08a-103">Group results by contiguous keys</span></span>

<span data-ttu-id="2d08a-104">下面的示例演示如何将元素分组为表示连续键子序列的区块。</span><span class="sxs-lookup"><span data-stu-id="2d08a-104">The following example shows how to group elements into chunks that represent subsequences of contiguous keys.</span></span> <span data-ttu-id="2d08a-105">例如，假设给定下列键值对的序列：</span><span class="sxs-lookup"><span data-stu-id="2d08a-105">For example, assume that you are given the following sequence of key-value pairs:</span></span>

|<span data-ttu-id="2d08a-106">键</span><span class="sxs-lookup"><span data-stu-id="2d08a-106">Key</span></span>|<span data-ttu-id="2d08a-107">“值”</span><span class="sxs-lookup"><span data-stu-id="2d08a-107">Value</span></span>|
|---------|-----------|
|<span data-ttu-id="2d08a-108">包含当前请求的 URL 的</span><span class="sxs-lookup"><span data-stu-id="2d08a-108">A</span></span>|<span data-ttu-id="2d08a-109">We</span><span class="sxs-lookup"><span data-stu-id="2d08a-109">We</span></span>|
|<span data-ttu-id="2d08a-110">包含当前请求的 URL 的</span><span class="sxs-lookup"><span data-stu-id="2d08a-110">A</span></span>|<span data-ttu-id="2d08a-111">think</span><span class="sxs-lookup"><span data-stu-id="2d08a-111">think</span></span>|
|<span data-ttu-id="2d08a-112">包含当前请求的 URL 的</span><span class="sxs-lookup"><span data-stu-id="2d08a-112">A</span></span>|<span data-ttu-id="2d08a-113">that</span><span class="sxs-lookup"><span data-stu-id="2d08a-113">that</span></span>|
|<span data-ttu-id="2d08a-114">B</span><span class="sxs-lookup"><span data-stu-id="2d08a-114">B</span></span>|<span data-ttu-id="2d08a-115">Linq</span><span class="sxs-lookup"><span data-stu-id="2d08a-115">Linq</span></span>|
|<span data-ttu-id="2d08a-116">C</span><span class="sxs-lookup"><span data-stu-id="2d08a-116">C</span></span>|<span data-ttu-id="2d08a-117">is</span><span class="sxs-lookup"><span data-stu-id="2d08a-117">is</span></span>|
|<span data-ttu-id="2d08a-118">包含当前请求的 URL 的</span><span class="sxs-lookup"><span data-stu-id="2d08a-118">A</span></span>|<span data-ttu-id="2d08a-119">really</span><span class="sxs-lookup"><span data-stu-id="2d08a-119">really</span></span>|
|<span data-ttu-id="2d08a-120">B</span><span class="sxs-lookup"><span data-stu-id="2d08a-120">B</span></span>|<span data-ttu-id="2d08a-121">cool</span><span class="sxs-lookup"><span data-stu-id="2d08a-121">cool</span></span>|
|<span data-ttu-id="2d08a-122">B</span><span class="sxs-lookup"><span data-stu-id="2d08a-122">B</span></span>|<span data-ttu-id="2d08a-123">!</span><span class="sxs-lookup"><span data-stu-id="2d08a-123">!</span></span>|

<span data-ttu-id="2d08a-124">以下组将按此顺序创建：</span><span class="sxs-lookup"><span data-stu-id="2d08a-124">The following groups will be created in this order:</span></span>

1. <span data-ttu-id="2d08a-125">We, think, that</span><span class="sxs-lookup"><span data-stu-id="2d08a-125">We, think, that</span></span>

2. <span data-ttu-id="2d08a-126">Linq</span><span class="sxs-lookup"><span data-stu-id="2d08a-126">Linq</span></span>

3. <span data-ttu-id="2d08a-127">is</span><span class="sxs-lookup"><span data-stu-id="2d08a-127">is</span></span>

4. <span data-ttu-id="2d08a-128">really</span><span class="sxs-lookup"><span data-stu-id="2d08a-128">really</span></span>

5. <span data-ttu-id="2d08a-129">cool, !</span><span class="sxs-lookup"><span data-stu-id="2d08a-129">cool, !</span></span>

<span data-ttu-id="2d08a-130">此解决方案是以扩展方法实现的，该扩展方法是线程安全的，并以流的方式返回其结果。</span><span class="sxs-lookup"><span data-stu-id="2d08a-130">The solution is implemented as an extension method that is thread-safe and that returns its results in a streaming manner.</span></span> <span data-ttu-id="2d08a-131">换言之，它在源序列中遍历移动时生成其组。</span><span class="sxs-lookup"><span data-stu-id="2d08a-131">In other words, it produces its groups as it moves through the source sequence.</span></span> <span data-ttu-id="2d08a-132">与 `group` 或 `orderby` 运算符不同，它能在所有序列被读取之前开始将组返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="2d08a-132">Unlike the `group` or `orderby` operators, it can begin returning groups to the caller before all of the sequence has been read.</span></span>

<span data-ttu-id="2d08a-133">线程安全通过在循环访问源序列的同时创建每个组或区块的副本来实现，如源代码注释中所述。</span><span class="sxs-lookup"><span data-stu-id="2d08a-133">Thread-safety is accomplished by making a copy of each group or chunk as the source sequence is iterated, as explained in the source code comments.</span></span> <span data-ttu-id="2d08a-134">如果源序列具有大型的连续项序列，则公共语言运行时可能会引发 <xref:System.OutOfMemoryException>。</span><span class="sxs-lookup"><span data-stu-id="2d08a-134">If the source sequence has a large sequence of contiguous items, the common language runtime may throw an <xref:System.OutOfMemoryException>.</span></span>

## <a name="example"></a><span data-ttu-id="2d08a-135">示例</span><span class="sxs-lookup"><span data-stu-id="2d08a-135">Example</span></span>

<span data-ttu-id="2d08a-136">下面的示例演示该扩展方法以及使用它的客户端代码：</span><span class="sxs-lookup"><span data-stu-id="2d08a-136">The following example shows both the extension method and the client code that uses it:</span></span>

[!code-csharp[cscsrefContiguousGroups#1](~/samples/snippets/csharp/concepts/linq/how-to-group-results-by-contiguous-keys_1.cs)]

<span data-ttu-id="2d08a-137">若要在项目中使用扩展方法，请将 `MyExtensions` 静态类复制到新的或现有源代码文件中，并且如有需要，请为它所在的命名空间添加 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="2d08a-137">To use the extension method in your project, copy the `MyExtensions` static class to a new or existing source code file and if it is required, add a `using` directive for the namespace where it is located.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d08a-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d08a-138">See also</span></span>

- [<span data-ttu-id="2d08a-139">语言集成查询 (LINQ)</span><span class="sxs-lookup"><span data-stu-id="2d08a-139">Language Integrated Query (LINQ)</span></span>](index.md)
