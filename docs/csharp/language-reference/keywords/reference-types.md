---
title: 引用类型（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: cca9826c658581be38866410d5f966b1c7c35772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267334"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="4e3a4-102">引用类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="4e3a4-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="4e3a4-103">C# 中有两种类型：引用类型和值类型。</span><span class="sxs-lookup"><span data-stu-id="4e3a4-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="4e3a4-104">引用类型的变量存储对其数据（对象）的引用，而值类型的变量直接包含其数据。</span><span class="sxs-lookup"><span data-stu-id="4e3a4-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="4e3a4-105">对于引用类型，两种变量可引用同一对象；因此，对一个变量执行的操作会影响另一个变量所引用的对象。</span><span class="sxs-lookup"><span data-stu-id="4e3a4-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="4e3a4-106">对于值类型，每个变量都具有其自己的数据副本，对一个变量执行的操作不会影响另一个变量（in、ref 和 out 参数变量除外；请参阅 [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md)、[ref](../../../csharp/language-reference/keywords/ref.md) 和 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数修饰符）。</span><span class="sxs-lookup"><span data-stu-id="4e3a4-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) and [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter modifier).</span></span>  
  
 <span data-ttu-id="4e3a4-107">下列关键字用于声明引用类型：</span><span class="sxs-lookup"><span data-stu-id="4e3a4-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="4e3a4-108">class</span><span class="sxs-lookup"><span data-stu-id="4e3a4-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="4e3a4-109">interface</span><span class="sxs-lookup"><span data-stu-id="4e3a4-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="4e3a4-110">delegate</span><span class="sxs-lookup"><span data-stu-id="4e3a4-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="4e3a4-111">C# 也提供了下列内置引用类型：</span><span class="sxs-lookup"><span data-stu-id="4e3a4-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="4e3a4-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="4e3a4-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="4e3a4-113">object</span><span class="sxs-lookup"><span data-stu-id="4e3a4-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="4e3a4-114">string</span><span class="sxs-lookup"><span data-stu-id="4e3a4-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="4e3a4-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e3a4-115">See Also</span></span>  
 [<span data-ttu-id="4e3a4-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="4e3a4-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4e3a4-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="4e3a4-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4e3a4-118">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="4e3a4-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4e3a4-119">类型</span><span class="sxs-lookup"><span data-stu-id="4e3a4-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="4e3a4-120">值类型</span><span class="sxs-lookup"><span data-stu-id="4e3a4-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
