---
title: "创建一个引用是为了嵌入的互操作程序集 &#39;&lt;assembly1&gt;&#39; 由于间接引用对该程序集从程序集 &#39;&lt;assembly2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40059
- bc40059
helpviewer_keywords:
- VBC40059
- BC40059
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aaaa7460ade00ad4232807ce11ee125e270742bf
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="a-reference-was-created-to-embedded-interop-assembly-39ltassembly1gt39-because-of-an-indirect-reference-to-that-assembly-from-assembly-39ltassembly2gt39"></a><span data-ttu-id="0ab2c-102">创建一个引用是为了嵌入的互操作程序集 &#39;&lt;assembly1&gt;&#39; 由于间接引用对该程序集从程序集 &#39;&lt;assembly2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="0ab2c-102">A reference was created to embedded interop assembly &#39;&lt;assembly1&gt;&#39; because of an indirect reference to that assembly from assembly &#39;&lt;assembly2&gt;&#39;</span></span>
<span data-ttu-id="0ab2c-103">创建了对嵌入的互操作程序集“\<assembly1>”的引用，因为程序集“\<assembly2>”间接引用了该程序集。</span><span class="sxs-lookup"><span data-stu-id="0ab2c-103">A reference was created to embedded interop assembly '\<assembly1>' because of an indirect reference to that assembly from assembly '\<assembly2>'.</span></span> <span data-ttu-id="0ab2c-104">请考虑更改任一程序集上的“Embed Interop Types”属性。</span><span class="sxs-lookup"><span data-stu-id="0ab2c-104">Consider changing the 'Embed Interop Types' property on either assembly.</span></span>  
  
 <span data-ttu-id="0ab2c-105">已添加对 `Embed Interop Types` 属性设置为 `True` 的程序集 (assembly1) 的引用。</span><span class="sxs-lookup"><span data-stu-id="0ab2c-105">You have added a reference to an assembly (assembly1) that has the `Embed Interop Types` property set to `True`.</span></span> <span data-ttu-id="0ab2c-106">这指示编译器嵌入来自该程序集的互操作类型信息。</span><span class="sxs-lookup"><span data-stu-id="0ab2c-106">This instructs the compiler to embed interop type information from that assembly.</span></span> <span data-ttu-id="0ab2c-107">但是，编译器不能嵌入来自该程序集的互操作类型信息，因为引用的另一个程序集 (assembly2) 也引用该程序集 (assembly1)，并将 `Embed Interop Types` 属性设置为 `False`。</span><span class="sxs-lookup"><span data-stu-id="0ab2c-107">However, the compiler cannot embed interop type information from that assembly because another assembly that you have referenced (assembly2) also references that assembly (assembly1) and has the `Embed Interop Types` property set to `False`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ab2c-108">将程序集引用的 `Embed Interop Types` 属性设置为 `True`，其效果等同于使用命令行编译器的 `/link` 选项引用该程序集。</span><span class="sxs-lookup"><span data-stu-id="0ab2c-108">Setting the `Embed Interop Types` property on an assembly reference to `True` is equivalent to referencing the assembly by using the `/link` option for the command-line compiler.</span></span>  
  
 <span data-ttu-id="0ab2c-109">**错误 ID:** BC40059</span><span class="sxs-lookup"><span data-stu-id="0ab2c-109">**Error ID:** BC40059</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="0ab2c-110">解决此警告</span><span class="sxs-lookup"><span data-stu-id="0ab2c-110">To address this warning</span></span>  
  
-   <span data-ttu-id="0ab2c-111">要嵌入这两个程序集的互操作类型信息，请将对 assembly1 的所有引用的 `Embed Interop Types` 属性设置为 `True`。</span><span class="sxs-lookup"><span data-stu-id="0ab2c-111">To embed interop type information for both assemblies, set the `Embed Interop Types` property on all references to assembly1 to `True`.</span></span>  
  
-   <span data-ttu-id="0ab2c-112">若要删除警告，可以将 assembly1 的 `Embed Interop Types` 属性设置为 `False`。</span><span class="sxs-lookup"><span data-stu-id="0ab2c-112">To remove the warning, you can set the `Embed Interop Types` property of assembly1 to `False`.</span></span> <span data-ttu-id="0ab2c-113">在这种情况下，由主互操作程序集 (PIA) 提供互操作类型信息。</span><span class="sxs-lookup"><span data-stu-id="0ab2c-113">In this case, interop type information is provided by a primary interop assembly (PIA).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ab2c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ab2c-114">See Also</span></span>  
 [<span data-ttu-id="0ab2c-115">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ab2c-115">/link (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/link.md)  
 [<span data-ttu-id="0ab2c-116">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="0ab2c-116">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
