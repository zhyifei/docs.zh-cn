---
title: "如何：调用 Windows API (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 772db789fba4552a4645d2c6a242ba01944652ee
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="0e33f-102">如何：调用 Windows API (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e33f-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="0e33f-103">此示例定义并调用`MessageBox`user32.dll 中的函数然后将字符串传递给它。</span><span class="sxs-lookup"><span data-stu-id="0e33f-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e33f-104">示例</span><span class="sxs-lookup"><span data-stu-id="0e33f-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0e33f-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="0e33f-105">Compiling the Code</span></span>  
 <span data-ttu-id="0e33f-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="0e33f-106">This example requires:</span></span>  
  
-   <span data-ttu-id="0e33f-107">对 <xref:System> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="0e33f-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0e33f-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="0e33f-108">Robust Programming</span></span>  
 <span data-ttu-id="0e33f-109">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="0e33f-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="0e33f-110">该方法不是静态的是抽象的或之前已定义。</span><span class="sxs-lookup"><span data-stu-id="0e33f-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="0e33f-111">父类型是接口或长度*名称*或*dll 名称*为零。</span><span class="sxs-lookup"><span data-stu-id="0e33f-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="0e33f-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="0e33f-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="0e33f-113">*名称*或*dll 名称*是`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="0e33f-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="0e33f-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="0e33f-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="0e33f-115">之前已使用 `CreateType` 创建包含类型。</span><span class="sxs-lookup"><span data-stu-id="0e33f-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="0e33f-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="0e33f-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e33f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e33f-117">See Also</span></span>  
 [<span data-ttu-id="0e33f-118">详述平台调用</span><span class="sxs-lookup"><span data-stu-id="0e33f-118">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="0e33f-119">平台调用示例</span><span class="sxs-lookup"><span data-stu-id="0e33f-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="0e33f-120">使用非托管 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="0e33f-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="0e33f-121">定义一个方法使用反射发出</span><span class="sxs-lookup"><span data-stu-id="0e33f-121">Defining a Method with Reflection Emit</span></span>](http://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [<span data-ttu-id="0e33f-122">演练：调用 Windows API</span><span class="sxs-lookup"><span data-stu-id="0e33f-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="0e33f-123">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="0e33f-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
