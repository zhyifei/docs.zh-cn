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
ms.openlocfilehash: 996e8a50f90c738bbc64c200125a785c0e9bcd58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a><span data-ttu-id="2351f-102">使用 &#39;FileGetObject &#39;而不是 &#39;FileGet &#39;当使用自变量的类型和 #39; 对象 &#39;</span><span class="sxs-lookup"><span data-stu-id="2351f-102">Use &#39;FileGetObject&#39; instead of &#39;FileGet&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="2351f-103">`FileGet` 方法包含 `Object`类型的参数。</span><span class="sxs-lookup"><span data-stu-id="2351f-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="2351f-104">应使用`FileGetObject` 替代 `FileGet` ，以避免多义性。</span><span class="sxs-lookup"><span data-stu-id="2351f-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="2351f-105">请注意，与 `My.Computer.Filesystem` 或 `FileGet` 相比， `FileGetObject`提供的功能更易于使用且性能更高。</span><span class="sxs-lookup"><span data-stu-id="2351f-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2351f-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="2351f-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="2351f-107">将 `FileGet` 替换为 `FileGetObject`。</span><span class="sxs-lookup"><span data-stu-id="2351f-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="2351f-108">将 `Object` 参数强制转换为一个更明确的类型。</span><span class="sxs-lookup"><span data-stu-id="2351f-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2351f-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2351f-109">See Also</span></span>  
 [<span data-ttu-id="2351f-110">不在生成中： FileGetObject 函数</span><span class="sxs-lookup"><span data-stu-id="2351f-110">NOT IN BUILD: FileGetObject Function</span></span>](http://msdn.microsoft.com/en-us/3eda786b-d1ee-4b44-9dd7-0ea6bff072c0)  
 [<span data-ttu-id="2351f-111">My.Computer.FileSystem 对象</span><span class="sxs-lookup"><span data-stu-id="2351f-111">My.Computer.FileSystem Object</span></span>](../../visual-basic/language-reference/objects/my-computer-filesystem-object.md)
