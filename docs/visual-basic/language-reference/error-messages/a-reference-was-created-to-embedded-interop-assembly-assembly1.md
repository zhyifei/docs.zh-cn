---
title: 到嵌入的互操作程序集已创建的是引用&#39; &lt;assembly1&gt; &#39;由于间接引用该程序集的程序集从&#39; &lt;assembly2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
ms.openlocfilehash: 43a441b6b99988ae1b47969dde9c4bc815820767
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588127"
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a><span data-ttu-id="c27c0-102">到嵌入的互操作程序集已创建的是引用&#39; &lt;assembly1&gt; &#39;由于间接引用该程序集的程序集从&#39; &lt;assembly2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="c27c0-102">A reference was created to embedded interop assembly &#39;&lt;assembly1&gt;&#39; because of an indirect reference to that assembly from assembly &#39;&lt;assembly2&gt;&#39;</span></span>
<span data-ttu-id="c27c0-103">创建了对嵌入的互操作程序集“\<assembly1>”的引用，因为程序集“\<assembly2>”间接引用了该程序集。</span><span class="sxs-lookup"><span data-stu-id="c27c0-103">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'.</span></span> <span data-ttu-id="c27c0-104">请考虑更改任一程序集上的“Embed Interop Types”属性。</span><span class="sxs-lookup"><span data-stu-id="c27c0-104">Consider changing the 'Embed Interop Types' property on either assembly.</span></span>  
  
 <span data-ttu-id="c27c0-105">已添加对 `Embed Interop Types` 属性设置为 `True` 的程序集 (assembly1) 的引用。</span><span class="sxs-lookup"><span data-stu-id="c27c0-105">You have added a reference to an assembly (assembly1) that has the `Embed Interop Types` property set to `True`.</span></span> <span data-ttu-id="c27c0-106">这指示编译器嵌入来自该程序集的互操作类型信息。</span><span class="sxs-lookup"><span data-stu-id="c27c0-106">This instructs the compiler to embed interop type information from that assembly.</span></span> <span data-ttu-id="c27c0-107">但是，编译器不能嵌入来自该程序集的互操作类型信息，因为引用的另一个程序集 (assembly2) 也引用该程序集 (assembly1)，并将 `Embed Interop Types` 属性设置为 `False`。</span><span class="sxs-lookup"><span data-stu-id="c27c0-107">However, the compiler cannot embed interop type information from that assembly because another assembly that you have referenced (assembly2) also references that assembly (assembly1) and has the `Embed Interop Types` property set to `False`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c27c0-108">将程序集引用的 `Embed Interop Types` 属性设置为 `True`，其效果等同于使用命令行编译器的 `/link` 选项引用该程序集。</span><span class="sxs-lookup"><span data-stu-id="c27c0-108">Setting the `Embed Interop Types` property on an assembly reference to `True` is equivalent to referencing the assembly by using the `/link` option for the command-line compiler.</span></span>  
  
 <span data-ttu-id="c27c0-109">**错误 ID:** BC40059</span><span class="sxs-lookup"><span data-stu-id="c27c0-109">**Error ID:** BC40059</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="c27c0-110">解决此警告</span><span class="sxs-lookup"><span data-stu-id="c27c0-110">To address this warning</span></span>  
  
-   <span data-ttu-id="c27c0-111">要嵌入这两个程序集的互操作类型信息，请将对 assembly1 的所有引用的 `Embed Interop Types` 属性设置为 `True`。</span><span class="sxs-lookup"><span data-stu-id="c27c0-111">To embed interop type information for both assemblies, set the `Embed Interop Types` property on all references to assembly1 to `True`.</span></span>  
  
-   <span data-ttu-id="c27c0-112">若要删除警告，可以将 assembly1 的 `Embed Interop Types` 属性设置为 `False`。</span><span class="sxs-lookup"><span data-stu-id="c27c0-112">To remove the warning, you can set the `Embed Interop Types` property of assembly1 to `False`.</span></span> <span data-ttu-id="c27c0-113">在这种情况下，由主互操作程序集 (PIA) 提供互操作类型信息。</span><span class="sxs-lookup"><span data-stu-id="c27c0-113">In this case, interop type information is provided by a primary interop assembly (PIA).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c27c0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c27c0-114">See Also</span></span>  
 [<span data-ttu-id="c27c0-115">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c27c0-115">/link (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/link.md)  
 [<span data-ttu-id="c27c0-116">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="c27c0-116">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
