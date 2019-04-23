---
title: 友元程序集引用 <reference> 无效
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 0c1526e32ddc64cb4124c6f8205d58deef911dd6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298989"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="9d9fe-102">友元程序集引用\<引用 > 无效</span><span class="sxs-lookup"><span data-stu-id="9d9fe-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="9d9fe-103">友元程序集引用\<引用 > 无效。</span><span class="sxs-lookup"><span data-stu-id="9d9fe-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="9d9fe-104">用强名称签名的程序集必须在他们的 InternalsVisibleTo 声明中指定一个公钥。</span><span class="sxs-lookup"><span data-stu-id="9d9fe-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="9d9fe-105">程序集名称传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性构造函数将识别的强名称的程序集，但它不包括`PublicKey`属性。</span><span class="sxs-lookup"><span data-stu-id="9d9fe-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="9d9fe-106">**错误 ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="9d9fe-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9d9fe-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9d9fe-107">To correct this error</span></span>  
  
1. <span data-ttu-id="9d9fe-108">确定强名称的友元程序集的公钥。</span><span class="sxs-lookup"><span data-stu-id="9d9fe-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="9d9fe-109">将公钥包含为程序集名称的一部分传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>特性构造函数通过使用`PublicKey`属性。</span><span class="sxs-lookup"><span data-stu-id="9d9fe-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9fe-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d9fe-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="9d9fe-111">友元程序集</span><span class="sxs-lookup"><span data-stu-id="9d9fe-111">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
