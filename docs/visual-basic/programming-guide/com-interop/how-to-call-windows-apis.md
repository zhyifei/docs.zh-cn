---
title: 如何：调用 Windows API (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 081f4242ef5883a8b25b8819ba3aff835b1e6ac7
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44129690"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="abd40-102">如何：调用 Windows API (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abd40-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="abd40-103">此示例中定义和调用`MessageBox`user32.dll 中的函数，然后将字符串传递给它。</span><span class="sxs-lookup"><span data-stu-id="abd40-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abd40-104">示例</span><span class="sxs-lookup"><span data-stu-id="abd40-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="abd40-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="abd40-105">Compiling the Code</span></span>  
 <span data-ttu-id="abd40-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="abd40-106">This example requires:</span></span>  
  
-   <span data-ttu-id="abd40-107">对 <xref:System> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="abd40-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="abd40-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="abd40-108">Robust Programming</span></span>  
 <span data-ttu-id="abd40-109">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="abd40-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="abd40-110">该方法不是静态的是抽象的或之前已定义。</span><span class="sxs-lookup"><span data-stu-id="abd40-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="abd40-111">父类型是一个接口或长度*名称*或*dllName*为零。</span><span class="sxs-lookup"><span data-stu-id="abd40-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="abd40-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="abd40-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="abd40-113">*名称*或*dllName*是`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="abd40-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="abd40-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="abd40-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="abd40-115">之前已使用 `CreateType` 创建包含类型。</span><span class="sxs-lookup"><span data-stu-id="abd40-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="abd40-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="abd40-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd40-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="abd40-117">See also</span></span>

- [<span data-ttu-id="abd40-118">平台调用详解</span><span class="sxs-lookup"><span data-stu-id="abd40-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)  
- [<span data-ttu-id="abd40-119">平台调用示例</span><span class="sxs-lookup"><span data-stu-id="abd40-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
- [<span data-ttu-id="abd40-120">使用非托管 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="abd40-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
- [<span data-ttu-id="abd40-121">定义方法使用反射发出</span><span class="sxs-lookup"><span data-stu-id="abd40-121">Defining a Method with Reflection Emit</span></span>](https://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
- [<span data-ttu-id="abd40-122">演练：调用 Windows API</span><span class="sxs-lookup"><span data-stu-id="abd40-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
- [<span data-ttu-id="abd40-123">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="abd40-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
