---
title: 在使用 "Object" 类型的参数时，请使用 "FileGetObject"，而不要使用 "FileGet"
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: fdad64a4b35aa792c996d25a9fd72a9ce1126fbd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306919"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="cf706-102">在使用 "Object" 类型的参数时，请使用 "FileGetObject"，而不要使用 "FileGet"</span><span class="sxs-lookup"><span data-stu-id="cf706-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>
<span data-ttu-id="cf706-103">`FileGet` 方法包含 `Object`类型的参数。</span><span class="sxs-lookup"><span data-stu-id="cf706-103">The `FileGet` method includes an argument of type `Object`.</span></span> `FileGetObject` <span data-ttu-id="cf706-104">替代 `FileGet` ，以避免多义性。</span><span class="sxs-lookup"><span data-stu-id="cf706-104">should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="cf706-105">请注意，与 `FileGet` 或 `FileGetObject` 相比，`My.Computer.Filesystem` 提供的功能更易于使用且性能更高。</span><span class="sxs-lookup"><span data-stu-id="cf706-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf706-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="cf706-106">To correct this error</span></span>  
  
1. <span data-ttu-id="cf706-107">将 `FileGet` 替换为 `FileGetObject`。</span><span class="sxs-lookup"><span data-stu-id="cf706-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2. <span data-ttu-id="cf706-108">将 `Object` 参数强制转换为一个更明确的类型。</span><span class="sxs-lookup"><span data-stu-id="cf706-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf706-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf706-109">See also</span></span>

- [<span data-ttu-id="cf706-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="cf706-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
