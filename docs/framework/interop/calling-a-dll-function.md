---
title: 调用 DLL 函数
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b842f44711d38a996b9d710dbe8bd369d30c5443
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71051885"
---
# <a name="calling-a-dll-function"></a><span data-ttu-id="a843a-102">调用 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="a843a-102">Calling a DLL Function</span></span>
<span data-ttu-id="a843a-103">尽管调用非托管 DLL 函数与调用其他托管代码几乎完全相同，但有一些差异会使 DLL 函数一开始令人感到迷惑。</span><span class="sxs-lookup"><span data-stu-id="a843a-103">Although calling unmanaged DLL functions is nearly identical to calling other managed code, there are differences that can make DLL functions seem confusing at first.</span></span> <span data-ttu-id="a843a-104">本部分介绍的主题描述了与一些与调用相关的异常问题。</span><span class="sxs-lookup"><span data-stu-id="a843a-104">This section introduces topics that describe some of the unusual calling-related issues.</span></span>  
  
 <span data-ttu-id="a843a-105">从平台调用返回的结构必须是在托管代码和非托管代码中表示形式相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a843a-105">Structures that are returned from platform invoke calls must be data types that have the same representation in managed and unmanaged code.</span></span> <span data-ttu-id="a843a-106">这些类型称为 blittable 类型，因为它们不需要转换（请参阅 [Blittable 类型和非 Blittable 类型](blittable-and-non-blittable-types.md)）。</span><span class="sxs-lookup"><span data-stu-id="a843a-106">Such types are called *blittable types* because they do not require conversion (see [Blittable and Non-Blittable Types](blittable-and-non-blittable-types.md)).</span></span> <span data-ttu-id="a843a-107">若要调用返回类型为 non-blittable 结构的函数，可定义与 non-blittable 类型大小相同的 blittable 帮助程序类型，并在函数返回后转换数据。</span><span class="sxs-lookup"><span data-stu-id="a843a-107">To call a function that has a non-blittable structure as its return type, you can define a blittable helper type of the same size as the non-blittable type and convert the data after the function returns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a843a-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="a843a-108">In This Section</span></span>  
 [<span data-ttu-id="a843a-109">传递结构</span><span class="sxs-lookup"><span data-stu-id="a843a-109">Passing Structures</span></span>](passing-structures.md)  
 <span data-ttu-id="a843a-110">确定使用预定义布局传递数据结构的问题。</span><span class="sxs-lookup"><span data-stu-id="a843a-110">Identifies the issues of passing data structures with a predefined layout.</span></span>  
  
 [<span data-ttu-id="a843a-111">回调函数</span><span class="sxs-lookup"><span data-stu-id="a843a-111">Callback Functions</span></span>](callback-functions.md)  
 <span data-ttu-id="a843a-112">提供有关回调函数的基本信息。</span><span class="sxs-lookup"><span data-stu-id="a843a-112">Provides basic information about callback functions.</span></span>  
  
 [<span data-ttu-id="a843a-113">如何：实现回调函数</span><span class="sxs-lookup"><span data-stu-id="a843a-113">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)  
 <span data-ttu-id="a843a-114">描述如何在托管代码中实现回调函数。</span><span class="sxs-lookup"><span data-stu-id="a843a-114">Describes how to implement callback functions in managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a843a-115">相关章节</span><span class="sxs-lookup"><span data-stu-id="a843a-115">Related Sections</span></span>  
 [<span data-ttu-id="a843a-116">使用非托管 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="a843a-116">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="a843a-117">描述如何使用平台调用调用非托管 DLL 函数。</span><span class="sxs-lookup"><span data-stu-id="a843a-117">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="a843a-118">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="a843a-118">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="a843a-119">描述如何声明方法形参以及如何将实参传递给由非托管库导出的函数。</span><span class="sxs-lookup"><span data-stu-id="a843a-119">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>
