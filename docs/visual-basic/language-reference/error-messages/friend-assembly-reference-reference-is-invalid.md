---
title: 友元程序集引用&lt;引用&gt;无效
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: c47fae9c60dc04ee02b1ff015d3dde87b8920c02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587366"
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="b18b9-102">友元程序集引用&lt;引用&gt;无效</span><span class="sxs-lookup"><span data-stu-id="b18b9-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="b18b9-103">友元程序集引用\<引用 > 无效。</span><span class="sxs-lookup"><span data-stu-id="b18b9-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="b18b9-104">用强名称签名的程序集必须在他们的 InternalsVisibleTo 声明中指定一个公钥。</span><span class="sxs-lookup"><span data-stu-id="b18b9-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="b18b9-105">程序集名称传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性构造函数标识强名称的程序集，但它不包括`PublicKey`属性。</span><span class="sxs-lookup"><span data-stu-id="b18b9-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="b18b9-106">**错误 ID:** BC31535</span><span class="sxs-lookup"><span data-stu-id="b18b9-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b18b9-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b18b9-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="b18b9-108">确定具有强名称的友元程序集的公钥。</span><span class="sxs-lookup"><span data-stu-id="b18b9-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="b18b9-109">将公钥包含如程序集名称的一部分传递到<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性构造函数通过使用`PublicKey`属性。</span><span class="sxs-lookup"><span data-stu-id="b18b9-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b18b9-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="b18b9-110">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="b18b9-111">友元程序集</span><span class="sxs-lookup"><span data-stu-id="b18b9-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 

