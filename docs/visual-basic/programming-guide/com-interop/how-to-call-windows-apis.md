---
title: 如何：调用 Windows API
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 6f3c53243d7aeb73be81796d5ca185c3a3c41c72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348703"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="d30c0-102">如何：调用 Windows API (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d30c0-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="d30c0-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span><span class="sxs-lookup"><span data-stu-id="d30c0-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d30c0-104">示例</span><span class="sxs-lookup"><span data-stu-id="d30c0-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d30c0-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="d30c0-105">Compiling the Code</span></span>  
 <span data-ttu-id="d30c0-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d30c0-106">This example requires:</span></span>  
  
- <span data-ttu-id="d30c0-107">对 <xref:System> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="d30c0-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d30c0-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="d30c0-108">Robust Programming</span></span>  
 <span data-ttu-id="d30c0-109">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="d30c0-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="d30c0-110">The method is not static, is abstract, or has been previously defined.</span><span class="sxs-lookup"><span data-stu-id="d30c0-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="d30c0-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span><span class="sxs-lookup"><span data-stu-id="d30c0-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="d30c0-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="d30c0-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="d30c0-113">The *name* or *dllName* is `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d30c0-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="d30c0-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="d30c0-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="d30c0-115">之前已使用 `CreateType` 创建包含类型。</span><span class="sxs-lookup"><span data-stu-id="d30c0-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="d30c0-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="d30c0-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d30c0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d30c0-117">See also</span></span>

- [<span data-ttu-id="d30c0-118">平台调用详解</span><span class="sxs-lookup"><span data-stu-id="d30c0-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="d30c0-119">平台调用示例</span><span class="sxs-lookup"><span data-stu-id="d30c0-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="d30c0-120">使用非托管 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="d30c0-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="d30c0-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d30c0-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="d30c0-122">演练：调用 Windows API</span><span class="sxs-lookup"><span data-stu-id="d30c0-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="d30c0-123">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="d30c0-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
