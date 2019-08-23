---
title: 安全和公共只读数组字段
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d36009fa4fc7b9299708768fe34a75f1fde6797
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910735"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="61c4f-102">安全和公共只读数组字段</span><span class="sxs-lookup"><span data-stu-id="61c4f-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="61c4f-103">永远不要使用托管库中的只读公共数组字段来定义应用程序的边界行为或安全性, 因为可以修改只读公共数组字段。</span><span class="sxs-lookup"><span data-stu-id="61c4f-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61c4f-104">备注</span><span class="sxs-lookup"><span data-stu-id="61c4f-104">Remarks</span></span>  
 <span data-ttu-id="61c4f-105">某些 .NET framework 类包含包含特定于平台的边界参数的只读公共字段。</span><span class="sxs-lookup"><span data-stu-id="61c4f-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="61c4f-106">例如, <xref:System.IO.Path.InvalidPathChars>字段是描述文件路径字符串中不允许使用的字符的数组。</span><span class="sxs-lookup"><span data-stu-id="61c4f-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="61c4f-107">在 .NET Framework 中存在许多类似的字段。</span><span class="sxs-lookup"><span data-stu-id="61c4f-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="61c4f-108">类似<xref:System.IO.Path.InvalidPathChars>公共只读字段的值可以通过代码或共享代码应用程序域的代码进行修改。</span><span class="sxs-lookup"><span data-stu-id="61c4f-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="61c4f-109">不应使用类似于这样的只读公共数组字段来定义应用程序的边界行为。</span><span class="sxs-lookup"><span data-stu-id="61c4f-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="61c4f-110">如果这样做, 恶意代码可以更改边界定义, 并以意外的方式使用您的代码。</span><span class="sxs-lookup"><span data-stu-id="61c4f-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="61c4f-111">在 .NET Framework 版本2.0 及更高版本中, 应使用返回新数组的方法, 而不是使用公共数组字段。</span><span class="sxs-lookup"><span data-stu-id="61c4f-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="61c4f-112">例如, 应<xref:System.IO.Path.GetInvalidPathChars%2A>使用方法, 而<xref:System.IO.Path.InvalidPathChars>不是使用字段。</span><span class="sxs-lookup"><span data-stu-id="61c4f-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="61c4f-113">请注意, .NET Framework 类型不使用公共字段在内部定义边界类型。</span><span class="sxs-lookup"><span data-stu-id="61c4f-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="61c4f-114">相反, .NET Framework 使用单独的私有字段。</span><span class="sxs-lookup"><span data-stu-id="61c4f-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="61c4f-115">更改这些公共字段的值不会改变 .NET Framework 类型的行为。</span><span class="sxs-lookup"><span data-stu-id="61c4f-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c4f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="61c4f-116">See also</span></span>

- [<span data-ttu-id="61c4f-117">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="61c4f-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
