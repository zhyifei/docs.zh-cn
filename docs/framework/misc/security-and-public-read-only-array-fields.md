---
title: 安全和公共只读数组字段
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 215e8136b4bc3f2982cdb2d8382b0eca6a881f9b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217033"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="b74dc-102">安全和公共只读数组字段</span><span class="sxs-lookup"><span data-stu-id="b74dc-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="b74dc-103">永远不要使用托管库中的只读公共数组字段来定义应用程序的边界行为或安全性，因为可以修改只读公共数组字段。</span><span class="sxs-lookup"><span data-stu-id="b74dc-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b74dc-104">备注</span><span class="sxs-lookup"><span data-stu-id="b74dc-104">Remarks</span></span>  
 <span data-ttu-id="b74dc-105">某些 .NET framework 类包含包含特定于平台的边界参数的只读公共字段。</span><span class="sxs-lookup"><span data-stu-id="b74dc-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="b74dc-106">例如，"<xref:System.IO.Path.InvalidPathChars>" 字段是描述文件路径字符串中不允许的字符的数组。</span><span class="sxs-lookup"><span data-stu-id="b74dc-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="b74dc-107">在 .NET Framework 中存在许多类似的字段。</span><span class="sxs-lookup"><span data-stu-id="b74dc-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="b74dc-108">公共只读字段（如 <xref:System.IO.Path.InvalidPathChars>）的值可以通过代码或共享代码应用程序域的代码进行修改。</span><span class="sxs-lookup"><span data-stu-id="b74dc-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="b74dc-109">不应使用类似于这样的只读公共数组字段来定义应用程序的边界行为。</span><span class="sxs-lookup"><span data-stu-id="b74dc-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="b74dc-110">如果这样做，恶意代码可以更改边界定义，并以意外的方式使用您的代码。</span><span class="sxs-lookup"><span data-stu-id="b74dc-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="b74dc-111">在 .NET Framework 版本2.0 及更高版本中，应使用返回新数组的方法，而不是使用公共数组字段。</span><span class="sxs-lookup"><span data-stu-id="b74dc-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="b74dc-112">例如，你应该使用 <xref:System.IO.Path.GetInvalidPathChars%2A> 方法，而不是使用 <xref:System.IO.Path.InvalidPathChars> 字段。</span><span class="sxs-lookup"><span data-stu-id="b74dc-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="b74dc-113">请注意，.NET Framework 类型不使用公共字段在内部定义边界类型。</span><span class="sxs-lookup"><span data-stu-id="b74dc-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="b74dc-114">相反，.NET Framework 使用单独的私有字段。</span><span class="sxs-lookup"><span data-stu-id="b74dc-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="b74dc-115">更改这些公共字段的值不会改变 .NET Framework 类型的行为。</span><span class="sxs-lookup"><span data-stu-id="b74dc-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b74dc-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b74dc-116">See also</span></span>

- [<span data-ttu-id="b74dc-117">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="b74dc-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
