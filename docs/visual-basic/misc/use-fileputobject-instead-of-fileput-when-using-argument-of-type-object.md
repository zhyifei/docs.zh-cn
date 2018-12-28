---
title: 在使用 "Object" 类型的自变量时，请使用 "FilePutObject"，而不要使用 "FilePut"
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: df7d7c54992984bcb1684e41f60ae8361a3aed03
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2018
ms.locfileid: "53774220"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="2291d-102">在使用 "Object" 类型的自变量时，请使用 "FilePutObject"，而不要使用 "FilePut"</span><span class="sxs-lookup"><span data-stu-id="2291d-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>
<span data-ttu-id="2291d-103">`FilePut` 方法包含 `Object`类型的参数。</span><span class="sxs-lookup"><span data-stu-id="2291d-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="2291d-104">应使用`FilePutObject` 替代 `FilePut` ，以避免多义性。</span><span class="sxs-lookup"><span data-stu-id="2291d-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2291d-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="2291d-105">To correct this error</span></span>  
  
-   <span data-ttu-id="2291d-106">将 `FilePut` 替换为 `FilePutObject`。</span><span class="sxs-lookup"><span data-stu-id="2291d-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="2291d-107">将 `Object` 参数强制转换为一个更明确的类型。</span><span class="sxs-lookup"><span data-stu-id="2291d-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="2291d-108">使用 `My.Computer.FileSystem` 对象中的可用功能。</span><span class="sxs-lookup"><span data-stu-id="2291d-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2291d-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="2291d-109">See Also</span></span>  
   
 [<span data-ttu-id="2291d-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="2291d-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [<span data-ttu-id="2291d-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="2291d-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
