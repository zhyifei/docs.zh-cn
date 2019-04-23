---
ms.openlocfilehash: 1805c26f1eff46719f30de8a14ca6d35f01948a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774299"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a><span data-ttu-id="af850-101">Foreach 迭代器变量现在已在迭代范围内，因此闭包捕获语义会不同（在 C#5 中）</span><span class="sxs-lookup"><span data-stu-id="af850-101">Foreach iterator variable is now scoped within the iteration, so closure capturing semantics are different (in C#5)</span></span>

|   |   |
|---|---|
|<span data-ttu-id="af850-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="af850-102">Details</span></span>|<span data-ttu-id="af850-103">从 C# 5 (Visual Studio 2012) 开始，<code>foreach</code> 迭代器变量在迭代范围内。</span><span class="sxs-lookup"><span data-stu-id="af850-103">Beginning with C# 5 (Visual Studio 2012), <code>foreach</code> iterator variables are scoped within the iteration.</span></span> <span data-ttu-id="af850-104">如果代码以前依靠变量而不在 <code>foreach</code> 闭包内，这可能会导致中断。</span><span class="sxs-lookup"><span data-stu-id="af850-104">This can cause breaks if code was previously depending on the variables to not be included in the <code>foreach</code>'s closure.</span></span> <span data-ttu-id="af850-105">此更改的特征如下：传递到委托的迭代器变量将视为委托创建时它拥有的值，而非调用委托时它拥有的值。</span><span class="sxs-lookup"><span data-stu-id="af850-105">The symptom of this change is that an iterator variable passed to a delegate is treated as the value it has at the time the delegate is created, rather than the value it has at the time the delegate is invoked.</span></span>|
|<span data-ttu-id="af850-106">建议</span><span class="sxs-lookup"><span data-stu-id="af850-106">Suggestion</span></span>|<span data-ttu-id="af850-107">理想情况下，应更新代码以使用新的编译器行为。</span><span class="sxs-lookup"><span data-stu-id="af850-107">Ideally, code should be updated to expect the new compiler behavior.</span></span> <span data-ttu-id="af850-108">如果需要旧语义，迭代器变量可替换为显式置于循环范围外的单独变量。</span><span class="sxs-lookup"><span data-stu-id="af850-108">If the old semantics are required, the iterator variable can be replaced with a separate variable which is explicitly placed outside of the loop's scope.</span></span>|
|<span data-ttu-id="af850-109">范围</span><span class="sxs-lookup"><span data-stu-id="af850-109">Scope</span></span>|<span data-ttu-id="af850-110">主要</span><span class="sxs-lookup"><span data-stu-id="af850-110">Major</span></span>|
|<span data-ttu-id="af850-111">版本</span><span class="sxs-lookup"><span data-stu-id="af850-111">Version</span></span>|<span data-ttu-id="af850-112">4.5</span><span class="sxs-lookup"><span data-stu-id="af850-112">4.5</span></span>|
|<span data-ttu-id="af850-113">类型</span><span class="sxs-lookup"><span data-stu-id="af850-113">Type</span></span>|<span data-ttu-id="af850-114">重定目标</span><span class="sxs-lookup"><span data-stu-id="af850-114">Retargeting</span></span>|
