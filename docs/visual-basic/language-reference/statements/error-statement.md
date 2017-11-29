---
title: "Error 语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cd3245fd3e9e62b1b6443e9787c97808a0d179d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="error-statement"></a><span data-ttu-id="087c2-102">Error 语句</span><span class="sxs-lookup"><span data-stu-id="087c2-102">Error Statement</span></span>
<span data-ttu-id="087c2-103">模拟出错的匹配项。</span><span class="sxs-lookup"><span data-stu-id="087c2-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="087c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="087c2-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="087c2-105">部件</span><span class="sxs-lookup"><span data-stu-id="087c2-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="087c2-106">必需。</span><span class="sxs-lookup"><span data-stu-id="087c2-106">Required.</span></span> <span data-ttu-id="087c2-107">可以是任何有效的错误号。</span><span class="sxs-lookup"><span data-stu-id="087c2-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="087c2-108">备注</span><span class="sxs-lookup"><span data-stu-id="087c2-108">Remarks</span></span>  
 <span data-ttu-id="087c2-109">`Error`向后兼容性支持语句。</span><span class="sxs-lookup"><span data-stu-id="087c2-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="087c2-110">在新代码，尤其是在创建对象时，使用`Err`对象的`Raise`方法以生成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="087c2-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="087c2-111">如果`errornumber`定义，`Error`语句后的属性调用错误处理程序`Err`对象分配以下默认值：</span><span class="sxs-lookup"><span data-stu-id="087c2-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="087c2-112">属性</span><span class="sxs-lookup"><span data-stu-id="087c2-112">Property</span></span>|<span data-ttu-id="087c2-113">值</span><span class="sxs-lookup"><span data-stu-id="087c2-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="087c2-114">指定为参数的值`Error`语句。</span><span class="sxs-lookup"><span data-stu-id="087c2-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="087c2-115">可以是任何有效的错误号。</span><span class="sxs-lookup"><span data-stu-id="087c2-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="087c2-116">当前的 Visual Basic 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="087c2-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="087c2-117">字符串对应的返回值的表达式`Error`函数为指定`Number`，如果存在此字符串。</span><span class="sxs-lookup"><span data-stu-id="087c2-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="087c2-118">如果字符串不存在，`Description`包含零长度字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="087c2-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="087c2-119">完全限定的驱动器、 路径和相应的 Visual Basic 帮助文件的文件名。</span><span class="sxs-lookup"><span data-stu-id="087c2-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="087c2-120">相应的 Visual Basic 帮助文件对应的错误的上下文 ID`Number`属性。</span><span class="sxs-lookup"><span data-stu-id="087c2-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="087c2-121">为零。</span><span class="sxs-lookup"><span data-stu-id="087c2-121">Zero.</span></span>|  
  
 <span data-ttu-id="087c2-122">如果没有错误处理程序存在，或者如果未启用，创建并从显示一条错误消息`Err`对象属性。</span><span class="sxs-lookup"><span data-stu-id="087c2-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="087c2-123">某些 Visual Basic 主机应用程序无法创建对象。</span><span class="sxs-lookup"><span data-stu-id="087c2-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="087c2-124">请参阅主机应用程序的文档，以确定它是否可以创建类和对象。</span><span class="sxs-lookup"><span data-stu-id="087c2-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="087c2-125">示例</span><span class="sxs-lookup"><span data-stu-id="087c2-125">Example</span></span>  
 <span data-ttu-id="087c2-126">此示例使用`Error`语句生成错误号 11。</span><span class="sxs-lookup"><span data-stu-id="087c2-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="087c2-127">要求</span><span class="sxs-lookup"><span data-stu-id="087c2-127">Requirements</span></span>  
 <span data-ttu-id="087c2-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="087c2-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="087c2-129">**程序集：** Visual Basic 运行库 （在 Microsoft.VisualBasic.dll 中)</span><span class="sxs-lookup"><span data-stu-id="087c2-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="087c2-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="087c2-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [<span data-ttu-id="087c2-131">On Error 语句</span><span class="sxs-lookup"><span data-stu-id="087c2-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [<span data-ttu-id="087c2-132">Resume 语句</span><span class="sxs-lookup"><span data-stu-id="087c2-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="087c2-133">错误消息</span><span class="sxs-lookup"><span data-stu-id="087c2-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
