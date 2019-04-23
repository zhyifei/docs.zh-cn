---
title: 回调函数
ms.date: 03/30/2017
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65f5e11a8fb40527387c14cdd8dec7f0bfc5c697
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196991"
---
# <a name="callback-functions"></a><span data-ttu-id="7a577-102">回调函数</span><span class="sxs-lookup"><span data-stu-id="7a577-102">Callback Functions</span></span>
<span data-ttu-id="7a577-103">回调函数是托管应用程序中的代码，可帮助非托管 DLL 函数完成一项任务。</span><span class="sxs-lookup"><span data-stu-id="7a577-103">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="7a577-104">对回调函数的调用间接从托管应用程序中进行传递、经过 DLL 函数，再回到托管实现。</span><span class="sxs-lookup"><span data-stu-id="7a577-104">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="7a577-105">一些通过平台调用的 DLL 函数需要托管代码中的回调函数才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="7a577-105">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="7a577-106">若要从托管代码中调用大部分 DLL 函数，则可以创建函数的托管定义，然后再调用它。</span><span class="sxs-lookup"><span data-stu-id="7a577-106">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="7a577-107">此过程相当简单。</span><span class="sxs-lookup"><span data-stu-id="7a577-107">The process is straightforward.</span></span>  
  
 <span data-ttu-id="7a577-108">使用需要回调函数的 DLL 函数还有一些其他步骤。</span><span class="sxs-lookup"><span data-stu-id="7a577-108">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="7a577-109">首先，必须通过查看函数的文档来确定该函数是否需要回调。</span><span class="sxs-lookup"><span data-stu-id="7a577-109">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="7a577-110">然后，需要在托管应用程序中创建回调函数。</span><span class="sxs-lookup"><span data-stu-id="7a577-110">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="7a577-111">最后，调用 DLL 函数，将指针作为一个参数传递给回调函数。</span><span class="sxs-lookup"><span data-stu-id="7a577-111">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span> 
 
 <span data-ttu-id="7a577-112">下图汇总了回调函数和实现步骤：</span><span class="sxs-lookup"><span data-stu-id="7a577-112">The following illustration summarizes the callback function and implementation steps:</span></span>  
  
 ![显示平台调用回调过程的图。](./media/callback-functions/platform-invoke-callback-process.gif)  
  
 <span data-ttu-id="7a577-114">回调函数非常适合用于需要重复执行一项任务的情况。</span><span class="sxs-lookup"><span data-stu-id="7a577-114">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="7a577-115">另一个常见用法是与枚举函数配合使用，如 Windows API 中的“EnumFontFamilies”、“EnumPrinters”和“EnumWindows”。</span><span class="sxs-lookup"><span data-stu-id="7a577-115">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Windows API.</span></span> <span data-ttu-id="7a577-116">EnumWindows 函数通过计算机上所有现有的窗口进行枚举，调用每个窗口上的回调函数以执行任务。</span><span class="sxs-lookup"><span data-stu-id="7a577-116">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="7a577-117">有关说明和示例，请参阅[如何：实现回调函数](../../../docs/framework/interop/how-to-implement-callback-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="7a577-117">For instructions and an example, see [How to: Implement Callback Functions](../../../docs/framework/interop/how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a577-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a577-118">See also</span></span>

- [<span data-ttu-id="7a577-119">如何：实现回调函数</span><span class="sxs-lookup"><span data-stu-id="7a577-119">How to: Implement Callback Functions</span></span>](../../../docs/framework/interop/how-to-implement-callback-functions.md)
- [<span data-ttu-id="7a577-120">调用 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="7a577-120">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)
