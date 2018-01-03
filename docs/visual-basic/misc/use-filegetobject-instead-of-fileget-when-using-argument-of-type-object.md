---
title: "使用 &#39;FileGetObject &#39;而不是 &#39;FileGet &#39;当使用自变量的类型和 #39; 对象 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c5be466a8a0339bdb57818755d85a26d632d774
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a><span data-ttu-id="77482-102">使用 &#39;FileGetObject &#39;而不是 &#39;FileGet &#39;当使用自变量的类型和 #39; 对象 &#39;</span><span class="sxs-lookup"><span data-stu-id="77482-102">Use &#39;FileGetObject&#39; instead of &#39;FileGet&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="77482-103">`FileGet` 方法包含 `Object`类型的参数。</span><span class="sxs-lookup"><span data-stu-id="77482-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="77482-104">应使用`FileGetObject` 替代 `FileGet` ，以避免多义性。</span><span class="sxs-lookup"><span data-stu-id="77482-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="77482-105">请注意，与 `My.Computer.Filesystem` 或 `FileGet` 相比， `FileGetObject`提供的功能更易于使用且性能更高。</span><span class="sxs-lookup"><span data-stu-id="77482-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="77482-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="77482-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="77482-107">将 `FileGet` 替换为 `FileGetObject`。</span><span class="sxs-lookup"><span data-stu-id="77482-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="77482-108">将 `Object` 参数强制转换为一个更明确的类型。</span><span class="sxs-lookup"><span data-stu-id="77482-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77482-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="77482-109">See Also</span></span>  
   
 [<span data-ttu-id="77482-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="77482-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
