---
title: 方法参数 - C# 参考
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 2cc7f9178fa5c1a040be9d45ba66fac292bb0e28
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713377"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="55886-102">方法参数（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="55886-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="55886-103">为不具有 [in](./in-parameter-modifier.md)、[ref](./ref.md) 或 [out](./out-parameter-modifier.md) 的方法声明的参数会按值传递给调用的方法。</span><span class="sxs-lookup"><span data-stu-id="55886-103">Parameters declared for a method without [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="55886-104">可以在方法中更改该值，但当控制传递回调用过程时，不会保留更改后的值。</span><span class="sxs-lookup"><span data-stu-id="55886-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="55886-105">可以通过使用方法参数关键字更改此行为。</span><span class="sxs-lookup"><span data-stu-id="55886-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="55886-106">本部分介绍声明方法参数时可以使用的关键字：</span><span class="sxs-lookup"><span data-stu-id="55886-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="55886-107">[params](./params.md) 指定此参数采用可变数量的参数。</span><span class="sxs-lookup"><span data-stu-id="55886-107">[params](./params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="55886-108">[in](./in-parameter-modifier.md) 指定此参数由引用传递，但只由调用方法读取。</span><span class="sxs-lookup"><span data-stu-id="55886-108">[in](./in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="55886-109">[ref](./ref.md) 指定此参数由引用传递，可能由调用方法读取或写入。</span><span class="sxs-lookup"><span data-stu-id="55886-109">[ref](./ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="55886-110">[out](./out-parameter-modifier.md) 指定此参数由引用传递，由调用方法写入。</span><span class="sxs-lookup"><span data-stu-id="55886-110">[out](./out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="55886-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="55886-111">See also</span></span>

- [<span data-ttu-id="55886-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="55886-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="55886-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="55886-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="55886-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="55886-114">C# Keywords</span></span>](./index.md)
