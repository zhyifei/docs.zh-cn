---
title: "使用 &#39;FilePutObject &#39;而不是 &#39;FilePut &#39;当使用自变量的类型和 #39; 对象 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5612c2bd4dc08f767643d2cd865a2ba1a8210c15
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a><span data-ttu-id="d45a0-102">使用 &#39;FilePutObject &#39;而不是 &#39;FilePut &#39;当使用自变量的类型和 #39; 对象 &#39;</span><span class="sxs-lookup"><span data-stu-id="d45a0-102">Use &#39;FilePutObject&#39; instead of &#39;FilePut&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="d45a0-103">`FilePut`方法包含类型的自变量`Object`。</span><span class="sxs-lookup"><span data-stu-id="d45a0-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="d45a0-104">应使用`FilePutObject` 替代 `FilePut` ，以避免多义性。</span><span class="sxs-lookup"><span data-stu-id="d45a0-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d45a0-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d45a0-105">To correct this error</span></span>  
  
-   <span data-ttu-id="d45a0-106">将 `FilePut` 替换为 `FilePutObject`。</span><span class="sxs-lookup"><span data-stu-id="d45a0-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="d45a0-107">将 `Object` 参数强制转换为一个更明确的类型。</span><span class="sxs-lookup"><span data-stu-id="d45a0-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="d45a0-108">使用 `My.Computer.FileSystem` 对象中的可用功能。</span><span class="sxs-lookup"><span data-stu-id="d45a0-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d45a0-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="d45a0-109">See Also</span></span>  
   
 [<span data-ttu-id="d45a0-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="d45a0-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [<span data-ttu-id="d45a0-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="d45a0-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
