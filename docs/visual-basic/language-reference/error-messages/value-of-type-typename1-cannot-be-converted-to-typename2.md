---
title: "值的类型 &#39;&lt;typename1&gt;&#39; 不能转换为 &#39;&lt;typename2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords: BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b583c4272dd6e964de99fb14d2795152c655f3aa
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a><span data-ttu-id="047eb-102">值的类型 &#39;&lt;typename1&gt;&#39; 不能转换为 &#39;&lt;typename2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="047eb-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="047eb-103">类型的值\<typename1 > 不能转换为\<typename2 >。</span><span class="sxs-lookup"><span data-stu-id="047eb-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="047eb-104">类型不匹配可能是由于文件引用与程序集的项目引用混合使用\<程序集名称 >。</span><span class="sxs-lookup"><span data-stu-id="047eb-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="047eb-105">请尝试替换为对的文件引用\<filepath > 项目中\<projectname1 > 的项目引用与\<项目名称 2> >。</span><span class="sxs-lookup"><span data-stu-id="047eb-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="047eb-106">在项目中进行项目引用和文件引用的情况下，编译器不能保证一个类型可转换为另一个。</span><span class="sxs-lookup"><span data-stu-id="047eb-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="047eb-107">下面的伪代码说明可以生成此错误的情况。</span><span class="sxs-lookup"><span data-stu-id="047eb-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="047eb-108">项目`P1`通过项目间接的项目引用`P2`到项目`P3`，同时还对直接文件引用`P3`。</span><span class="sxs-lookup"><span data-stu-id="047eb-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="047eb-109">声明`commonObject`使用对的文件引用`P3`，而对的调用`P2.getCommonClass`使用到的项目引用`P3`。</span><span class="sxs-lookup"><span data-stu-id="047eb-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="047eb-110">这种情况下的问题是文件引用指定的文件路径和名称的输出文件`P3`(通常为 p3.dll)，而项目引用标识源项目 (`P3`) 按项目名称。</span><span class="sxs-lookup"><span data-stu-id="047eb-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="047eb-111">因此，编译器也不能保证类型`P3.commonClass`来自通过两个不同引用相同的源代码。</span><span class="sxs-lookup"><span data-stu-id="047eb-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="047eb-112">这种情况通常发生在项目引用和混合文件引用。</span><span class="sxs-lookup"><span data-stu-id="047eb-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="047eb-113">上图中，问题可能不会发生如果`P1`所做的直接项目引用`P3`而不是文件引用。</span><span class="sxs-lookup"><span data-stu-id="047eb-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="047eb-114">**错误 ID:** BC30955</span><span class="sxs-lookup"><span data-stu-id="047eb-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="047eb-115">更正此错误</span><span class="sxs-lookup"><span data-stu-id="047eb-115">To correct this error</span></span>  
  
-   <span data-ttu-id="047eb-116">更改对项目引用的文件引用。</span><span class="sxs-lookup"><span data-stu-id="047eb-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047eb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="047eb-117">See Also</span></span>  
 [<span data-ttu-id="047eb-118">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="047eb-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="047eb-119">管理项目中的引用</span><span class="sxs-lookup"><span data-stu-id="047eb-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 
