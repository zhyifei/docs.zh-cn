---
title: 在使用 "Object" 类型的自变量时，请使用 "FilePutObject"，而不要使用 "FilePut"
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 3d793151905c61ee12eccdfdb5e9567a4924bb35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022514"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="46ec8-102">在使用 "Object" 类型的自变量时，请使用 "FilePutObject"，而不要使用 "FilePut"</span><span class="sxs-lookup"><span data-stu-id="46ec8-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>
<span data-ttu-id="46ec8-103">`FilePut` 方法包含 `Object`类型的参数。</span><span class="sxs-lookup"><span data-stu-id="46ec8-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="46ec8-104">应使用`FilePutObject` 替代 `FilePut` ，以避免多义性。</span><span class="sxs-lookup"><span data-stu-id="46ec8-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46ec8-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="46ec8-105">To correct this error</span></span>  
  
- <span data-ttu-id="46ec8-106">将 `FilePut` 替换为 `FilePutObject`。</span><span class="sxs-lookup"><span data-stu-id="46ec8-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
- <span data-ttu-id="46ec8-107">将 `Object` 参数强制转换为一个更明确的类型。</span><span class="sxs-lookup"><span data-stu-id="46ec8-107">Cast the `Object` argument to a more specific type.</span></span>  
  
- <span data-ttu-id="46ec8-108">使用 `My.Computer.FileSystem` 对象中的可用功能。</span><span class="sxs-lookup"><span data-stu-id="46ec8-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ec8-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="46ec8-109">See also</span></span>

- [<span data-ttu-id="46ec8-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="46ec8-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="46ec8-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="46ec8-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
