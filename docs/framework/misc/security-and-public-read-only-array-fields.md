---
title: 安全和公共只读数组字段
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19b5ad73150697c1442056642a1b11d504ecc426
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113771"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="3be6b-102">安全和公共只读数组字段</span><span class="sxs-lookup"><span data-stu-id="3be6b-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="3be6b-103">切勿使用托管库的只读公共数组字段来定义边界行为或应用程序的安全性，因为可以修改公共的只读数组字段。</span><span class="sxs-lookup"><span data-stu-id="3be6b-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3be6b-104">备注</span><span class="sxs-lookup"><span data-stu-id="3be6b-104">Remarks</span></span>  
 <span data-ttu-id="3be6b-105">某些.NET framework 类包括只读、 只包含特定于平台的边界参数的公共字段。</span><span class="sxs-lookup"><span data-stu-id="3be6b-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="3be6b-106">例如，<xref:System.IO.Path.InvalidPathChars>字段是一个数组，其中描述的文件路径字符串中不允许使用的字符。</span><span class="sxs-lookup"><span data-stu-id="3be6b-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="3be6b-107">许多类似字段是存在于整个.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="3be6b-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="3be6b-108">公共只读字段的值如<xref:System.IO.Path.InvalidPathChars>可以通过代码或共享您的代码的应用程序域的代码修改。</span><span class="sxs-lookup"><span data-stu-id="3be6b-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="3be6b-109">不应使用如下的只读公共数组字段来定义您的应用程序边界行为。</span><span class="sxs-lookup"><span data-stu-id="3be6b-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="3be6b-110">如果这样做，恶意代码可以更改边界定义，并以意外的方式使用你的代码。</span><span class="sxs-lookup"><span data-stu-id="3be6b-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="3be6b-111">在版本 2.0 及更高版本的.NET Framework 中，应使用返回一个新数组，而不是使用公共数组字段的方法。</span><span class="sxs-lookup"><span data-stu-id="3be6b-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="3be6b-112">例如，而不是使用<xref:System.IO.Path.InvalidPathChars>字段中，应使用<xref:System.IO.Path.GetInvalidPathChars%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="3be6b-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="3be6b-113">请注意，.NET Framework 类型不使用公共字段在内部定义边界类型。</span><span class="sxs-lookup"><span data-stu-id="3be6b-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="3be6b-114">相反，.NET Framework 使用单独的私有字段。</span><span class="sxs-lookup"><span data-stu-id="3be6b-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="3be6b-115">更改这些公共字段的值不会更改.NET Framework 类型的行为。</span><span class="sxs-lookup"><span data-stu-id="3be6b-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be6b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="3be6b-116">See also</span></span>

- [<span data-ttu-id="3be6b-117">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="3be6b-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
